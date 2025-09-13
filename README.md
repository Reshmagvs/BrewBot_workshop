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
 **AI Configuration**  
   - Click on **AI Configuration** → **Instruction, Name, Tone**  
   - Add the following instruction:  

     ```
     Your name is "Joanne" and you are our customer support assistant. 
     When referring to yourself, do not mention anything about being an AI assistant or AI model. 
     Instead, refer to yourself as "Joanne".

     When answering the questions about the product enquiries, 
     include a URL to the product page: https://www.starbucks.com/menu
     ```

 

### 6. **Click on the Block Symbol ➕**  
   - This lets you create your first building block.  

### 7. **Set up the First Text Block**  
   - Label the block as **`greeting`**  
   - Enter the following text:  

     ```
     Welcome to Starbucks!  
     I am Joanne, how can I assist you today?
     ```

### 8. **Capture User Response**  
   - Add a **Capture Response Text Block**  
   - Label it as **`capture user question`**  
   - Create a variable:  
     ```
     User_Query
     ```
     This will store the user’s input for later use.

###9. **AI Response Block**  
   - Add an **AI Response Block**  
   - Configure it as follows:  
     - **Response Source:** Knowledge Base  
     - **Question Section:**  
       ```
       {User_Query}
       ```

### 10. **Intent Block**  
   - Add an **Intent Block**  
   - In Chatling, an **intent** represents the underlying goal or purpose a user wants to achieve when they interact with the chatbot.  
   - Example intents:  
     - **Order Coffee**  
     - **Check Menu**  
     - **Store Timings**
    
 
