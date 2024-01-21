# strapi-google-cloud-storage

This package provides a convenient way to integrate Google Cloud Storage with Strapi, an open-source headless CMS. It allows you to upload and manage your media files on Google Cloud Storage directly from your Strapi admin panel.

## Features

- Easy integration with Strapi projects.
- Upload, delete, and manage media files stored in Google Cloud Storage.
- Configurable bucket access and file paths.

## Installation

```bash
npm install strapi-google-cloud-storage
```

or

```bash
yarn add strapi-google-cloud-storage
```

## Configuration

1. **Google Cloud Service Account:** Ensure you have a Google Cloud service account with permissions to access the necessary storage buckets.

2. **Create a Bucket:** Create a bucket in Google Cloud Storage where your files will be stored.

3. **Setup Strapi Provider:** In your Strapi project, configure the provider in `config/plugins.js`:

   ```javascript
   module.exports = {
     // ...
     upload: {
       provider: 'google-cloud-storage',
       providerOptions: {
         bucketName: 'your-bucket-name',
         publicFiles: true,
         uniform: false,
         basePath: '',
         serviceAccount: {
           type: 'service_account',
           project_id: 'your-project-id',
           private_key_id: 'your-private-key-id',
           private_key: 'your-private-key',
           client_email: 'your-client-email',
           client_id: 'your-client-id',
           auth_uri: 'https://accounts.google.com/o/oauth2/auth',
           token_uri: 'https://oauth2.googleapis.com/token',
           auth_provider_x509_cert_url: 'https://www.googleapis.com/oauth2/v1/certs',
           client_x509_cert_url: 'your-cert-url'
         },
       },
     },
     // ...
   };
   ```

## Usage

Once configured, the Strapi media library will automatically use Google Cloud Storage to store new files. You can upload, view, and delete files from your Strapi admin panel.

## Advanced Configuration

- **Caching:** You can enable caching for better performance.
- **File Access:** Configure whether files are public or private.
- **Path Customization:** Customize the file path and naming conventions in your bucket.

## Contributing

Contributions are welcome. Please submit a pull request or open an issue for any features or fixes.

## License

This project is licensed under the MIT License.

---

Remember to replace placeholder values like `your-bucket-name`, `your-project-id`, etc., with actual values from your Google Cloud Storage configuration. You should also include any additional information specific to the use or configuration of the package that might be helpful to users.