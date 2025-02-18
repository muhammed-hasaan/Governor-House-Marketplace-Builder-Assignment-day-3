# README - Day 3: API Integration and Data Migration

## Objective
The objective of Day 3 was to integrate an external API and migrate data into Sanity CMS to build a dynamic and functional marketplace backend. This involved testing API endpoints, transforming data, updating schemas, and ensuring successful data rendering in the frontend.

---

## Steps Performed

### 1. **Understanding the API**
- **API URL**: `https://hackathon-apis.vercel.app/api/products`
- The API provided product information, categories, and images.
- Endpoints were tested using **Postman** to validate responses.

### 2. **Setting Up the Backend**
- **Tools Used**:
  - `axios`: For fetching data from the external API.
  - `next-sanity`: For interacting with Sanity CMS.
  - `slugify`: To generate clean slugs for product names.

### 3. **Sanity Schema Adjustments**
- Updated the `product` schema to include fields like `tags`, `dimensions`, and `category`.
- Created a `category` schema to store product categories.
- Established a reference field in the `product` schema to link with the `category` schema.

### 4. **Data Migration**
- **Process**:
  1. Fetched data from the external API using `axios`.
  2. Uploaded images to Sanity CMS and retrieved image references.
  3. Transformed the API data to match the Sanity schema structure.
  4. Imported the transformed data into Sanity CMS using the `createOrReplace` method.

- **Error Handling**:
  - Used `try-catch` blocks to handle errors during API calls and migrations.
  - Logged errors for debugging purposes.

### 5. **Frontend Integration**
- Created reusable backend functions to fetch data from Sanity CMS:
  - `getAllProducts`: Fetches all products.
  - `getPopularProducts`: Fetches popular or featured products.
  - `getProductBySlug`: Retrieves product details using a slug.
- Rendered the imported data in the frontend and verified its accuracy.

---

## Challenges and Solutions

### 1. **Large Image Files**
- **Challenge**: Handling large image files during migration.
- **Solution**: Uploaded images using the Sanity asset manager with buffer support.

### 2. **Schema Mismatches**
- **Challenge**: Mismatches between the API fields and the Sanity schema.
- **Solution**: Adjusted schemas and mapped fields in the migration script.

### 3. **Data Integrity**
- **Challenge**: Ensuring accurate data migration without loss.
- **Solution**: Added validation checks for missing or malformed data before importing.

---

## Performance Optimizations
- Batched API requests to avoid rate limits and improve speed.
- Cached commonly fetched API responses.
- Limited query fields to reduce the size of data being fetched.

---

## Results
- Successfully imported **products** and **categories** into Sanity CMS.
- Verified the data in the Sanity CMS Studio.
- Displayed the imported data in the frontend marketplace.

---

## Future Improvements
- Automate schema validation to catch mismatches before migration.
- Add detailed logging for better error tracking.
- Implement real-time data syncing using Sanity webhooks.

---

## How to Run the Migration Script

1. **Prerequisites**:
   - Node.js installed.
   - Sanity project set up and connected.
   - External API accessible.

2. **Steps**:
   - Clone the repository and navigate to the project directory:
     ```bash
     git clone [repository-url]
     cd [project-directory]
     ```
   - Install dependencies:
     ```bash
     npm install
     ```
   - Run the migration script:
     ```bash
     node scripts/importData.js
     ```

3. **Verify Results**:
   - Open Sanity CMS Studio to confirm the imported data.
   - Check the frontend to ensure the product listings and categories are displayed.

---

## Conclusion
Day 3 successfully demonstrated the integration of external API data into Sanity CMS. The migration process ensured data integrity, scalability, and flexibility for future development. This workflow prepared the system to handle dynamic data and adapt to evolving project requirements.
