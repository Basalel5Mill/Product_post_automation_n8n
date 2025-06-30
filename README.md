# Product Post Automation Workflow

This n8n workflow automates cross‑platform social media publishing for HASKYN’s Product Post. It generates tailored captions, uploads images, and publishes to Instagram, X (formerly Twitter), and LinkedIn — all in one seamless process.

---

## 🛠️ Purpose & Intention

As HASKYN grew, manually crafting and publishing posts across multiple channels became time‑consuming and error prone. This workflow was created to:

* **Save time** by automating repetitive publishing tasks.
* **Ensure consistency** in brand voice and hashtags across platforms.
* **Scale effortlessly** as our content needs expand.
* **Enable non‑technical teams** to maintain an active social presence.

---

## 📖 Story: From Frustration to Flow

Every Monday, Emily, HASKYN’s marketing lead, spent hours crafting captions, resizing images, and juggling credentials to post on Instagram, X, and LinkedIn. Late nights and countless copy‑paste mistakes eroded her creativity.

One day, she sketched a plan:

1. **AI‑powered caption generator** for platform‑specific tone.
2. **Automated image upload** to cloud storage.
3. **Unified publish** step for each network.

By modeling this in n8n, Emily now hits **one button**, and her posts go live everywhere — freeing her to focus on strategy and storytelling.

---

## ⚙️ How It Works

1. **Webhook Trigger**: Receives a post request with image and metadata.
2. **AI Captioning**: A LangChain node generates JSON captions for Instagram, X, and LinkedIn.
3. **Image Handling**:

   * Downloads source image from Google Drive.
   * Uploads to Google Cloud Storage and sets public access.
4. **Field Mapping**: Sets platform‑specific parameters (caption text, media IDs).
5. **Publish Steps**:

   * **Create Container** on Instagram Graph API.
   * **Publish** to Instagram, X (via Twitter node), and LinkedIn.
6. **Wait Node**: Ensures Instagram’s container is ready before publishing.

---

## 🚀 Business Benefits

* **Faster Time‑to‑Market**: Publish new product posts in minutes instead of hours.
* **Brand Consistency**: Captions and hashtags stay uniform across channels.
* **Reduced Errors**: Automated field mapping eliminates copy‑paste mistakes.
* **Scalability**: Add new platforms or content types by inserting nodes.

---

## 🔌 Front‑end Integration

To integrate with your front‑end or CMS:

1. **Expose the Webhook URL** from the n8n Webhook node.
2. **Send a POST** with JSON payload:

   ```json
   {
     "node": "17841470359168338",
     "image url": "https://.../my-product.jpg",
     "text": "Your product description here"
   }
   ```
3. **Trigger** the workflow; the post will publish automatically.

For custom front‑end hooks or authentication layers, wrap the POST call in your favorite framework (React, Vue, or plain JS).

---

## 📬 Contact & Support

For questions, customizations, or integration help:

* **Email**: [support@haskyn.com](mailto:basalelr@gmail.com
)

