# pro2-frontend
This repo includes the UI code of the chatbot


the considerations for making the env UI ready are as follows

### ✅ Step 1: Set up the frontend project locally
1. Make sure you have **Node.js** and **npm** installed on your machine.
   - Run: `node -v` and `npm -v` to check.

2. Create a project folder and initialize it:
   ```bash
   npx create-react-app chatbot-ui
   cd chatbot-ui
   ```

3. Install Tailwind CSS:
   Follow [Tailwind’s React guide](https://tailwindcss.com/docs/guides/create-react-app) or just run:
   ```bash
   npm install -D tailwindcss postcss autoprefixer
   npx tailwindcss init -p
   ```

4. Configure `tailwind.config.js` and add Tailwind directives to your `index.css`.

5. Add the **code I gave** into your `App.jsx` or `Chatbot.jsx`.

---

### ✅ Step 2: **Connect the frontend to a backend**
You need to build the backend API endpoint `/api/chat`. Here's how:

- This will be handled by **API Gateway + Lambda**.
- Lambda will call **Amazon Bedrock** to get chatbot responses.

You can temporarily **mock this** in your frontend until the backend is ready:
```js
const response = await fetch('/api/chat', {
  method: 'POST',
  body: JSON.stringify({ message: userInput }),
});
```

---

### ✅ Step 3: **Deploy frontend using AWS Amplify**
This takes care of hosting your UI and setting up a CDN.

1. Push your code to **GitHub**.
2. Go to [Amplify Console](https://console.aws.amazon.com/amplify/).
3. Click “New app” → “Host web app”.
4. Connect your GitHub repo.
5. Select the branch, Amplify will auto-deploy it.

---

### ✅ Step 4: **Prepare the backend**
You’ll need to:
- Set up API Gateway → Lambda (Node.js/Python)
- Write a Lambda function to call **Amazon Bedrock** (chat model)
- Connect to **DynamoDB** to log conversations
- Add **Amazon Cognito** for login/auth (optional now, but good later)

---

### 🚀 Suggestion for Next Step:
Want me to help you write the **backend Lambda function** that takes the user’s input and returns a response from **Bedrock**?

We can build that next and test it with the frontend.

Let me know!
