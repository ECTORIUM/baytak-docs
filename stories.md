# Baytak Property Management - User Stories

## Epics

*   **EPIC-ORG:** Organisation & User Management
*   **EPIC-PROP:** Property Portfolio Management
*   **EPIC-TEN:** Tenant & Lease Management
*   **EPIC-OPS:** Property Operations (Maintenance, Inspections, Documents)

---

## Organisation & User Management (EPIC-ORG)

*   **STORY-ORG-1:** As an Administrator, I want to create a new Organisation record with its name, contact details, address, and website, so that I can set up the primary entity managing properties.
*   **STORY-ORG-2:** As an Administrator, I want to view and edit the details of an existing Organisation, so that I can keep the information up-to-date.
*   **STORY-USER-1:** As an Organisation Administrator, I want to create new User accounts (e.g., property managers) associated with my Organisation, including their name, email, phone, and role, so that staff can access the system.
*   **STORY-USER-2:** As an Organisation Administrator, I want to set a User's status to active or inactive, so that I can manage access for employees who join or leave.
*   **STORY-USER-3:** As an Organisation Administrator, I want to view and edit User details (except password), so that I can correct information or update roles.
*   **STORY-USER-4:** As a User, I want to log in using my email and password, so that I can access the application's features based on my role.
*   **STORY-USER-5:** As a User, I want to be able to reset my password, so that I can regain access if I forget it.
*   **STORY-USER-6:** As an Administrator, I want the system to track the last login time for users, so that I can monitor account activity.

---

## Property Portfolio Management (EPIC-PROP)

*   **STORY-PTYPE-1:** As an Administrator, I want to manage (create, view, update, delete) Property Types (e.g., Residential, Commercial), so that properties can be categorized correctly.
*   **STORY-ATYPE-1:** As an Administrator, I want to manage (create, view, update, delete) Apartment Types (e.g., Condo, Loft, Studio), so that specific apartment styles can be defined.
*   **STORY-AMEN-1:** As an Administrator, I want to manage (create, view, update, delete) Amenities (e.g., Pool, Gym), so that these can be associated with properties.
*   **STORY-PROP-1:** As a Property Manager, I want to create a new Property record associated with my Organisation, including its name, description, address details, type, beds/baths, size, year built, etc., so that I can add inventory to the system.
*   **STORY-PROP-2:** As a Property Manager, I want to view a list of all properties managed by my Organisation, with basic filtering and sorting options, so that I can get an overview of the portfolio.
*   **STORY-PROP-3:** As a Property Manager, I want to view the detailed information for a specific Property, so that I can see all its attributes.
*   **STORY-PROP-4:** As a Property Manager, I want to edit the details of an existing Property, so that I can keep its information accurate (e.g., update status, description).
*   **STORY-PROP-5:** As a Property Manager, I want to specify parking information and pet policy for a Property, so that this information is available for listings and leases.
*   **STORY-PROP-6:** As a Property Manager, I want to associate a list of Amenities with a Property (potentially linking to the Amenities lookup), so that tenants know what features are available.
*   **STORY-PROP-7:** As a Property Manager, I want to upload multiple images for a Property, including setting a primary image and adding descriptions, so that I can visually represent the property.
*   **STORY-PROP-8:** As a Property Manager, I want to view the images associated with a Property, so that I can manage the visual gallery.
*   **STORY-PROP-9:** As a Property Manager, I want to delete images associated with a Property, so that I can remove outdated or incorrect photos.
*   **STORY-PROP-10:** As a Property Manager, I want to set the status of a Property (e.g., Available, Rented, Under Maintenance), so that its current state is clear.

---

## Tenant & Lease Management (EPIC-TEN)

*   **STORY-TEN-1:** As a Property Manager, I want to create a new Tenant record associated with my Organisation, including their name and contact information, so that I can track individuals renting properties.
*   **STORY-TEN-2:** As a Property Manager, I want to view a list of all Tenants associated with my Organisation, so that I can manage tenant records.
*   **STORY-TEN-3:** As a Property Manager, I want to view the detailed information for a specific Tenant, so that I can access their contact details.
*   **STORY-TEN-4:** As a Property Manager, I want to edit the details of an existing Tenant, so that I can keep their contact information up-to-date.
*   **STORY-LEASE-1:** As a Property Manager, I want to create a new Lease agreement, linking a specific Tenant to a specific Property within my Organisation, so that I can formalize a rental contract.
*   **STORY-LEASE-2:** As a Property Manager, I want to specify the lease duration, start date, end date, monthly price, rent due day, and security deposit amount for a Lease, so that the core financial and temporal terms are defined.
*   **STORY-LEASE-3:** As a Property Manager, I want to record the late fee policy and renewal terms for a Lease, so that these conditions are documented.
*   **STORY-LEASE-4:** As a Property Manager, I want to set the status of a Lease (e.g., Started, Ended, Cancelled), so that its current state is tracked.
*   **STORY-LEASE-5:** As a Property Manager, I want to view a list of all Leases, filterable by Property, Tenant, or status, so that I can manage active and past agreements.
*   **STORY-LEASE-6:** As a Property Manager, I want to view the details of a specific Lease, including the linked Tenant and Property information, so that I can review the agreement terms.
*   **STORY-LEASE-7:** As a Property Manager, I want to edit the details of an existing Lease (e.g., add notes, update status), so that I can manage the agreement over its lifecycle.

---

## Property Operations (EPIC-OPS)

*   **STORY-MAINT-1:** As a Property Manager, I want to record a Maintenance Request reported for a Property (potentially linked to a Tenant), including the description, reported date, priority, and initial status ('Open'), so that I can track reported issues.
*   **STORY-MAINT-2:** As a Property Manager, I want to view a list of Maintenance Requests, filterable by Property, status, or priority, so that I can manage ongoing repairs.
*   **STORY-MAINT-3:** As a Property Manager, I want to update the status of a Maintenance Request (e.g., 'In Progress', 'Resolved', 'Cancelled'), so that the workflow is tracked.
*   **STORY-MAINT-4:** As a Property Manager, I want to add resolution details and a resolved date to a Maintenance Request, so that the outcome is documented.
*   **STORY-DOC-1:** As a Property Manager, I want to upload documents (e.g., PDF, DOCX, JPG) and associate them with an Organisation, Property, Tenant, or Lease, so that important files are stored centrally.
*   **STORY-DOC-2:** As a Property Manager, I want to specify the document type and add a description for an uploaded document, so that it can be easily identified.
*   **STORY-DOC-3:** As a Property Manager, I want to view a list of documents associated with a specific Property, Tenant, or Lease, so that I can find relevant files easily.
*   **STORY-DOC-4:** As a Property Manager, I want to download an uploaded document, so that I can view or share it outside the system.
*   **STORY-DOC-5:** As a Property Manager, I want to delete an uploaded document, so that I can remove irrelevant or outdated files.
*   **STORY-INSP-1:** As a Property Manager, I want to record a Property Inspection, linking it to a Property and specifying the date, inspector (User), and type ('Move-In', 'Move-Out', 'Periodic'), so that property condition checks are documented.
*   **STORY-INSP-2:** As a Property Manager, I want to add notes and detailed condition ratings (potentially as structured data or text) to a Property Inspection record, so that the findings are captured.
*   **STORY-INSP-3:** As a Property Manager, I want to optionally upload a tenant signature associated with a Property Inspection, so that acknowledgement can be recorded.
*   **STORY-INSP-4:** As a Property Manager, I want to view a list of past Inspections for a specific Property, so that I can review the inspection history.