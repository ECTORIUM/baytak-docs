# Project Documentation

Welcome to the documentation for this project.

## Table of Contents

- [Introduction](#introduction)
- [Models](#models)
  - [Organisations](#organisations)
  - [Users](#users)
  - [Property Types](#property-types)
  - [Apartment Types](#apartment-types)
  - [Amenities](#amenities)
  - [Properties](#properties)
  - [Property Images](#property-images)
  - [Tenants](#tenants)
  - [Lease](#lease)
  - [Maintenance Requests](#maintenance-requests)
  - [Documents](#documents)
  - [Property Inspections](#property-inspections)


## Introduction

Brief introduction to your project.

## Models

This section outlines the data models used in the Baytak property management application.

### Organisations

Represents the top-level entity, typically a property management company or landlord entity, that owns properties and manages users and tenants.

| Name             | Data Type | Description                                  | Example                     |
|------------------|-----------|----------------------------------------------|-----------------------------|
| `id`             | UUID      | Unique identifier for the organisation       | `a1b2c3d4-e5f6-7890-1234-567890abcdef` |
| `name`           | String    | Name of the organisation                     | "Acme Property Management"  |
| `contact_email`  | String    | Primary contact email for the organisation   | "contact@acmeproperty.com"  |
| `phone_number`   | String    | Primary contact phone number                 | "+1-555-111-2222"           |
| `address`        | String    | Physical address of the organisation's office| "456 Business Rd, Suite 100, Anytown, USA" |
| `website`        | String    | Organisation's website URL                   | "https://www.acmeproperty.com" |
| `created_at`     | Timestamp | When the organisation record was created     | `2023-10-27T10:00:00Z`      |
| `updated_at`     | Timestamp | When the organisation record was last updated | `2023-10-27T10:00:00Z`      |

### Users

Represents individuals who have access to the application, typically employees or administrators of an organisation. Each user belongs to one organisation.

| Name             | Data Type | Description                                  | Example                     |
|------------------|-----------|----------------------------------------------|-----------------------------|
| `id`             | UUID      | Unique identifier for the user               | `b2c3d4e5-f6a7-8901-2345-67890abcdef0` |
| `organisation_id`| UUID      | Foreign key linking to the Organisations table | `a1b2c3d4-e5f6-7890-1234-567890abcdef` |
| `first_name`     | String    | User's first name                            | "Alice"                     |
| `last_name`      | String    | User's last name                             | "Smith"                     |
| `email`          | String    | User's email address (used for login)        | "alice.smith@acmeproperty.com" |
| `phone_number`   | String    | User's contact phone number                  | "+1-555-333-4444"           |
| `password_hash`  | String    | Hashed password for security                 | `$2b$12$abcdef...`          |
| `role`           | String    | User's role (e.g., 'admin', 'manager')       | "manager"                   |
| `is_active`      | Boolean   | Flag indicating if the user account is active| true                        |
| `last_login_at`  | Timestamp | Timestamp of the user's last login           | `2024-05-15T14:30:00Z`      |
| `created_at`     | Timestamp | When the user record was created             | `2023-10-27T10:05:00Z`      |
| `updated_at`     | Timestamp | When the user record was last updated        | `2024-05-15T14:30:00Z`      |

### Property Types

Lookup table defining the general categories of properties.

| Name             | Data Type | Description                                  | Example                     |
|------------------|-----------|----------------------------------------------|-----------------------------|
| `id`             | UUID      | Unique identifier for the property type      | `f6a7b8c9-d0e1-2345-6789-0abcdef01234` |
| `name`           | String    | Name of the property type                    | "Residential"               |
| `description`    | Text      | Optional description of the property type    | "Properties used for living purposes." |
| `created_at`     | Timestamp | When the property type record was created    | `2023-10-27T10:08:00Z`      |
| `updated_at`     | Timestamp | When the property type record was last updated| `2023-10-27T10:08:00Z`      |

### Apartment Types

Lookup table defining specific types of apartments, used when `PropertyType` is relevant (e.g., Residential).

| Name             | Data Type | Description                                  | Example                     |
|------------------|-----------|----------------------------------------------|-----------------------------|
| `id`             | UUID      | Unique identifier for the apartment type     | `a7b8c9d0-e1f2-3456-7890-1abcdef012345` |
| `name`           | String    | Name of the apartment type                   | "Condo"                     |
| `description`    | Text      | Optional description of the apartment type   | "Individually owned unit within a larger complex." |
| `created_at`     | Timestamp | When the apartment type record was created   | `2023-10-27T10:09:00Z`      |
| `updated_at`     | Timestamp | When the apartment type record was last updated| `2023-10-27T10:09:00Z`      |

### Amenities

Lookup table defining available amenities for properties. This could be linked to Properties via a join table for a many-to-many relationship if needed.

| Name             | Data Type | Description                                  | Example                     |
|------------------|-----------|----------------------------------------------|-----------------------------|
| `id`             | UUID      | Unique identifier for the amenity            | `c9d0e1f2-a3b4-5678-9012-345678abcdef` |
| `name`           | String    | Name of the amenity                          | "Swimming Pool"             |
| `description`    | Text      | Optional description of the amenity          | "Outdoor, seasonal swimming pool." |
| `created_at`     | Timestamp | When the amenity record was created          | `2023-10-27T10:07:00Z`      |
| `updated_at`     | Timestamp | When the amenity record was last updated     | `2023-10-27T10:07:00Z`      |

### Properties

Represents the physical properties (e.g., apartments, houses) managed by an organisation. Each property belongs to one organisation.

| Name                | Data Type        | Description                                      | Example                     |
|---------------------|------------------|--------------------------------------------------|-----------------------------|
| `id`                | UUID             | Unique identifier for the property               | `c3d4e5f6-a7b8-9012-3456-7890abcdef01` |
| `organisation_id`   | UUID             | Foreign key linking to the Organisations table     | `a1b2c3d4-e5f6-7890-1234-567890abcdef` |
| `name`              | String           | A descriptive name for the property              | "Sunny Downtown Apartment"  |
| `description`       | Text             | Detailed description of the property             | "Bright 2-bed apartment with city views." |
| `status`            | String/Enum      | Current status of the property                   | "Available"                 |
| `baths`             | Float            | Number of bathrooms                              | 1.5                         |
| `bedrooms`          | Integer          | Number of bedrooms                               | 2                           |
| `size_sqft`         | Integer          | Size of the property in square feet              | 950                         |
| `year_built`        | Integer          | The year the property was built                  | 1998                        |
| `address`           | String           | Street address line                              | "123 Main St"               |
| `city`              | String           | City where the property is located               | "Anytown"                   |
| `house_number`      | String           | House or apartment number                        | "Apt 4B"                    |
| `area`              | String           | Neighborhood or area                             | "Downtown"                  |
| `country`           | String           | Country where the property is located            | "USA"                       |
| `zip_code`          | String           | Postal or ZIP code                               | "12345"                     |
| `number_of_guests`  | Integer          | Maximum number of guests allowed                 | 4                           |
| `property_type`     | String           | General type of property                         | "Residential"               |
| `apartment_type`    | String           | Specific type if it's an apartment               | "Condo"                     |
| `parking_info`      | String/Text      | Details about parking availability               | "1 assigned garage spot"    |
| `pet_policy`        | String/Enum      | Policy regarding pets                            | "Cats Only"                 |
| `amenities`         | Array/JSON/Text  | List of amenities                                | ["Pool", "Gym"]             |
| `images`            | Array/JSON/Text  | List of image URLs or identifiers                | ["img1.jpg", "img2.jpg"]    |
| `security_deposit`  | Decimal          | Amount required for security deposit             | 1000.00                     |
| `latitude`          | Float            | Geographic coordinate - latitude                 | 34.0522                     |
| `longitude`         | Float            | Geographic coordinate - longitude                | -118.2437                   |
| `created_at`        | Timestamp        | When the property record was created             | `2023-10-27T10:10:00Z`      |
| `updated_at`        | Timestamp        | When the property record was last updated        | `2024-05-10T11:00:00Z`      |

### Property Images

Stores image information associated with properties.

| Name             | Data Type | Description                                  | Example                     |
|------------------|-----------|----------------------------------------------|-----------------------------|
| `id`             | UUID      | Unique identifier for the property image     | `d0e1f2a3-b4c5-6789-0123-456789abcdef0` |
| `property_id`    | UUID      | Foreign key linking to the Properties table  | `c3d4e5f6-a7b8-9012-3456-7890abcdef01` |
| `image_url`      | String    | URL or path to the image file                | "/images/props/prop123_main.jpg" |
| `description`    | String    | Optional caption or description for the image| "Living room view"          |
| `is_primary`     | Boolean   | Indicates if this is the primary image       | true                        |
| `created_at`     | Timestamp | When the image record was created            | `2023-11-01T15:00:00Z`      |
| `updated_at`     | Timestamp | When the image record was last updated       | `2023-11-01T15:00:00Z`      |

### Tenants

Represents the individuals or entities renting a property from the organisation. Each tenant belongs to one organisation and is typically associated with one or more properties (though this simple model links them primarily to the organisation).

| Name             | Data Type | Description                                  | Example                     |
|------------------|-----------|----------------------------------------------|-----------------------------|
| `id`             | UUID      | Unique identifier for the tenant             | `d4e5f6a7-b8c9-0123-4567-890abcdef012` |
| `organisation_id`| UUID      | Foreign key linking to the Organisations table | `a1b2c3d4-e5f6-7890-1234-567890abcdef` |
| `name`           | String    | Full name of the tenant                      | "John Doe"                  |
| `email`          | String    | Tenant's email address                       | "john.doe@email.com"        |
| `phone_number`   | String    | Tenant's phone number                        | "+1-555-123-4567"           |
| `created_at`     | Timestamp | When the tenant record was created           | `2023-10-27T10:15:00Z`      |
| `updated_at`     | Timestamp | When the tenant record was last updated      | `2023-10-27T10:15:00Z`      |

### Lease

Represents the agreement between a tenant and the organisation for renting a specific property.

| Name             | Data Type   | Description                                      | Example                     |
|------------------|-------------|--------------------------------------------------|-----------------------------|
| `id`             | UUID        | Unique identifier for the lease                  | `e5f6a7b8-c9d0-1234-5678-90abcdef0123` |
| `organisation_id`| UUID        | Foreign key linking to the Organisations table     | `a1b2c3d4-e5f6-7890-1234-567890abcdef` |
| `property_id`    | UUID        | Foreign key linking to the Properties table      | `c3d4e5f6-a7b8-9012-3456-7890abcdef01` |
| `tenant_id`      | UUID        | Foreign key linking to the Tenants table         | `d4e5f6a7-b8c9-0123-4567-890abcdef012` |
| `duration`       | Integer     | Duration of the lease in months                  | 12                          |
| `start_date`     | Date        | The date the lease agreement begins              | `2024-01-01`                |
| `end_date`       | Date        | The date the lease agreement ends                | `2024-12-31`                |
| `status`         | String/Enum | Current status of the lease (`started`, `cancelled`, `ended`) | `started`                   |
| `price`          | Decimal     | Monthly rent price for this lease                | 1550.00                     |
| `rent_due_day`   | Integer     | Day of the month rent is due                     | 1                           |
| `late_fee_policy`| String/Text | Description of the late fee policy               | "$50 fee if paid after the 5th" |
| `renewal_terms`  | String/Text | Information about lease renewal options          | "Option to renew month-to-month after term" |
| `notes`          | Text        | Any additional notes specific to this lease      | "Tenant requested early move-in." |
| `created_at`     | Timestamp   | When the lease record was created                | `2023-12-15T09:00:00Z`      |
| `updated_at`     | Timestamp   | When the lease record was last updated           | `2024-01-05T11:00:00Z`      |

### Maintenance Requests

Tracks issues reported by tenants regarding properties.

| Name                | Data Type   | Description                                      | Example                     |
|---------------------|-------------|--------------------------------------------------|-----------------------------|
| `id`                | UUID        | Unique identifier for the maintenance request    | `b8c9d0e1-f2a3-4567-8901-234567abcdef` |
| `property_id`       | UUID        | Foreign key linking to the Properties table      | `c3d4e5f6-a7b8-9012-3456-7890abcdef01` |
| `tenant_id`         | UUID        | Foreign key linking to the Tenants table         | `d4e5f6a7-b8c9-0123-4567-890abcdef012` |
| `organisation_id`   | UUID        | Foreign key linking to the Organisations table     | `a1b2c3d4-e5f6-7890-1234-567890abcdef` |
| `reported_date`     | Timestamp   | When the issue was reported                      | `2024-05-20T09:30:00Z`      |
| `description`       | Text        | Detailed description of the issue                | "Leaky faucet in the kitchen sink." |
| `status`            | String/Enum | Current status (`Open`, `In Progress`, `Resolved`, `Cancelled`) | `Open`                      |
| `priority`          | String/Enum | Priority level (`Low`, `Medium`, `High`, `Urgent`) | `Medium`                    |
| `resolution_details`| Text        | Optional details about how the issue was resolved| "Plumber replaced washer."    |
| `resolved_date`     | Timestamp   | Optional timestamp when the issue was resolved   | `2024-05-21T14:00:00Z`      |
| `created_at`        | Timestamp   | When the maintenance request record was created  | `2024-05-20T09:30:00Z`      |
| `updated_at`        | Timestamp   | When the maintenance request record was last updated | `2024-05-21T14:00:00Z`      |

### Documents

Stores files like lease agreements, inspection reports, notices, tenant applications, etc.

| Name             | Data Type   | Description                                      | Example                     |
|------------------|-------------|--------------------------------------------------|-----------------------------|
| `id`             | UUID        | Unique identifier for the document               | `e1f2a3b4-c5d6-7890-1234-567890abcdef1` |
| `organisation_id`| UUID        | Foreign key linking to the Organisations table     | `a1b2c3d4-e5f6-7890-1234-567890abcdef` |
| `property_id`    | UUID        | Optional FK linking to the Properties table      | `c3d4e5f6-a7b8-9012-3456-7890abcdef01` |
| `tenant_id`      | UUID        | Optional FK linking to the Tenants table         | `d4e5f6a7-b8c9-0123-4567-890abcdef012` |
| `lease_id`       | UUID        | Optional FK linking to the Lease table           | `e5f6a7b8-c9d0-1234-5678-90abcdef0123` |
| `document_type`  | String/Enum | Type of document ('Lease Agreement', 'Notice', 'Inspection Report', etc.) | 'Lease Agreement'         |
| `file_url`       | String      | URL or path to the stored document file          | "/docs/org1/lease_johndoe.pdf" |
| `upload_date`    | Timestamp   | When the document was uploaded                   | `2023-12-10T11:00:00Z`      |
| `description`    | Text        | Optional description of the document             | "Signed lease agreement for John Doe" |
| `created_at`     | Timestamp   | When the document record was created             | `2023-12-10T11:00:00Z`      |
| `updated_at`     | Timestamp   | When the document record was last updated        | `2023-12-10T11:00:00Z`      |

### Property Inspections

Records the condition of a property at specific times (e.g., move-in, move-out).

| Name                 | Data Type   | Description                                      | Example                     |
|----------------------|-------------|--------------------------------------------------|-----------------------------|
| `id`                 | UUID        | Unique identifier for the inspection             | `f2a3b4c5-d6e7-8901-2345-67890abcdef12` |
| `property_id`        | UUID        | Foreign key linking to the Properties table      | `c3d4e5f6-a7b8-9012-3456-7890abcdef01` |
| `inspection_date`    | Date/Timestamp| Date and time of the inspection                | `2024-01-01T10:00:00Z`      |
| `inspector_id`       | UUID        | Foreign key linking to the Users table (inspector)| `b2c3d4e5-f6a7-8901-2345-67890abcdef0` |
| `inspection_type`    | String/Enum | Type of inspection ('Move-In', 'Move-Out', 'Periodic') | 'Move-In'                 |
| `notes`              | Text        | General notes about the inspection               | "Property clean, minor scuff on wall." |
| `condition_ratings`  | JSON/Text   | Detailed condition ratings (e.g., per room)    | `{"living_room": "Good", "kitchen": "Excellent"}` |
| `tenant_signature_url`| String      | Optional URL to the tenant's signature image/file| "/signatures/tenant_johndoe_movein.png" |
| `created_at`         | Timestamp   | When the inspection record was created           | `2024-01-01T10:30:00Z`      |
| `updated_at`         | Timestamp   | When the inspection record was last updated      | `2024-01-01T10:30:00Z`      |