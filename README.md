# ☕ AI Coffee Shop Assistant (No Code with Chatling)

This project shows how to build a **Coffee Shop AI Assistant** without writing a single line of code , powered by [Chatling](https://chatling.ai/).  

The assistant can:  
1. Answer questions about coffee products from a **custom knowledge base**.  
2. Track customer orders (via order number lookup).  
3. Hand off conversations to a **human agent** when needed.  

---

## 🚀 Steps to Create Your AI Coffee Shop Assistant

### 1. Create a Chatling Account
- Sign up for free at 👉 [https://chatling.ai/](https://chatling.ai/)

### 2. Download
Download these datasets to train the assistant:
- [Starbucks Company Profile (PDF)](https://about.starbucks.com/uploads/2023/02/AboutUs-Company-Profile-2.6.23.pdf)  
- [Starbucks Menu (PDF)](https://www.uwe.ac.uk/-/media/uwe/documents/life/starbucks-menu.pdf)

### 3. Create a New AI Chatbot
1. From the Chatling dashboard, click **New → AI Chatbot**.  
2. Choose **Web** as the platform.  
3. Select **Start From Scratch**.  

### 4. Add Knowledge Base
1. In the left sidebar, go to **Knowledge Base**.  
2. Upload the following PDFs:  
3. Once uploaded, the assistant will be able to answer questions like:  
   - *“I’m looking for a latte, any recommendations?”*  
   - *“Do you have vegan options?”*
    
![Knowledge Base Upload](https://github.com/Reshmagvs/BrewBot_workshop/blob/main/ww1.png)  

### 5. **Go to the Builder Section**  
   - This is where we will be building the entire framework.

### 6. **Click on the Block Symbol ➕**  
   - This lets you create your first building block.  

### 7. **Set up the First Text Block**  
   - Label the block as **`greeting`**  
   - Enter the following text:  

     ```
     Welcome to Starbucks!  
     I am Joanne, how can I assist you today?
     ```

