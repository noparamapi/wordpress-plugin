# NoParam Email Validation Plugin for WordPress  

NoParam is a privacy-first email validation API that helps prevent fake signups and invalid email addresses on your WordPress forms. This plugin integrates NoParam’s real-time email validation into popular form plugins to improve email list quality and reduce bounce rates.  

## 🚀 Features  
✅ **Real-time email validation** – Validate emails instantly as users type.  
✅ **Prevent fake signups** – Block disposable and invalid email addresses.  
✅ **Works with popular form plugins**:  
   - Contact Form 7  
   - WPForms  
   - More coming soon

✅ **Privacy-first** – No tracking, no storing, no reselling.  
✅ **Easy setup** – Just add your API key and start validating.  

## 📖 Installation  

### **From the WordPress Plugin Directory (Coming Soon)**  
1. Go to your WordPress admin dashboard.  
2. Navigate to **Plugins → Add New**.  
3. Search for **NoParam Email Validation**.  
4. Click **Install Now**, then **Activate**.  

### **Manual Installation**  
1. [Download the latest release](https://github.com/NoParamAPI/wordpress-plugin/releases).  
2. Upload the plugin folder to your WordPress `/wp-content/plugins/` directory.  
3. Activate the plugin from the WordPress admin panel under **Plugins**.  

## 🔧 Setup & Configuration  
1. Go to **Settings → NoParam Email Validation** in WordPress.  
2. Enter your **NoParam API Key** (Get one from [NoParam.com](https://noparam.com)).  
3. Choose which forms to enable validation for.  
4. Save changes and you're done! 🎉  

## 🛠️ Usage  
Once activated and configured, the plugin will automatically validate emails submitted through supported forms. Invalid email addresses will be rejected with an error message.  

## 📦 API Example  
For developers, NoParam offers a simple API:  

```php
$api_key = 'YOUR_API_KEY';
$email = 'example@email.com';

$response = wp_remote_get("https://noparam.com/api/v1/verify?email=$email", [
    'headers' => [
        'Authorization' => "Bearer $api_key"
    ]
]);

$body = wp_remote_retrieve_body($response);
$data = json_decode($body, true);
