# Technical Documentation: Supabase Data Schema
## Project: Apple Cabins Canada Ltd.

This document outlines the database schema required to support the features and user journeys designed for the Apple Cabins Canada Ltd. platform.

### 1. Database Overview
**Provider:** Supabase (PostgreSQL)
**Core Functionality:** User authentication, multi-tenant dashboards (Customer & Partner), inventory management, lead capture, and blog CMS.

---

### 2. Tables Schema

#### `profiles`
Extends Supabase Auth metadata to store user-specific information.
- `id`: uuid (references auth.users.id, primary key)
- `email`: text (unique)
- `full_name`: text
- `avatar_url`: text
- `role`: enum ('admin', 'partner', 'customer')
- `created_at`: timestamptz

#### `cabins_inventory`
Central repository for all modular units (Cabin, Capsule, and Home series).
- `id`: uuid (primary key)
- `model_name`: text (e.g., 'Nebula Space Capsule', 'Alpine Z')
- `series`: enum ('Cabin', 'Capsule', 'Home')
- `sq_ft`: integer
- `base_price`: numeric
- `csa_certified`: boolean (default: true)
- `stock_count`: integer
- `shipping_eta_days`: integer
- `specifications`: jsonb (stores technical details like insulation, materials, etc.)
- `image_urls`: text[] (array of DataStore image links)

#### `properties`
Units deployed or available at specific resort locations.
- `id`: uuid (primary key)
- `owner_id`: uuid (references profiles.id)
- `cabin_model_id`: uuid (references cabins_inventory.id)
- `status`: enum ('available', 'rented', 'maintenance', 'occupied')
- `location_region`: text (e.g., 'Squamish', 'Greater Vancouver')
- `resort_name`: text
- `current_lease_start`: date
- `current_lease_end`: date
- `guest_rating`: numeric

#### `inquiries`
Captures leads from the "Configure Your Cabin" and "Partner Onboarding" flows.
- `id`: uuid (primary key)
- `user_id`: uuid (optional, references profiles.id)
- `type`: enum ('purchase', 'partnership')
- `first_name`: text
- `last_name`: text
- `email`: text
- `phone`: text
- `property_location`: text
- `details`: jsonb (stores configuration choices, acreage, zoning, etc.)
- `status`: enum ('new', 'contacted', 'qualified', 'closed')

#### `payouts`
Financial records for resort partners.
- `id`: uuid (primary key)
- `partner_id`: uuid (references profiles.id)
- `property_id`: uuid (references properties.id)
- `amount`: numeric
- `currency`: text (default: 'CAD')
- `status`: enum ('initiated', 'processing', 'completed', 'failed')
- `transaction_date`: timestamptz

#### `blog_posts`
CMS data for the Admin Blog Management section.
- `id`: uuid (primary key)
- `author_id`: uuid (references profiles.id)
- `title`: text
- `slug`: text (unique)
- `content`: text (markdown or HTML)
- `featured_image`: text
- `seo_metadata`: jsonb
- `published_at`: timestamptz (null if draft)

---

### 3. Row Level Security (RLS) Policies

To ensure data privacy between partners and customers:

- **Profiles:** Users can read/write their own profile only. Admins can read all.
- **Properties:** Partners can only view properties linked to their `owner_id`. Customers can view all 'available' properties.
- **Inquiries:** Users can view their own inquiries. Admins can view/edit all.
- **Payouts:** Partners can only view payouts linked to their `partner_id`.

### 4. Storage Buckets
- `cabin-assets`: Public bucket for cabin photos and technical specs.
- `user-uploads`: Private bucket for partner documents and property photos.
- `blog-media`: Public bucket for blog post imagery.