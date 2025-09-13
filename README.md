# ☕ AI Coffee Shop Assistant (No Code with Chatling)

This project shows how to build a **Coffee Shop AI Assistant** without writing a single line of code , powered by [Chatling](https://chatling.ai/).  

The assistant can:  
1. Answer questions about coffee products from a **custom knowledge base**.  
2. Track customer orders (via order number lookup).  
3. Hand off conversations to a **human agent** when needed.  

---

## Steps to Create Your AI Coffee Shop Assistant

1. Create a Chatling Account
- Sign up for free at 👉 [https://chatling.ai/](https://chatling.ai/)

2. Download
Download these datasets to train the assistant:
- [Starbucks Company Profile (PDF)](https://about.starbucks.com/uploads/2023/02/AboutUs-Company-Profile-2.6.23.pdf)  
- [Starbucks Menu (PDF)](https://www.uwe.ac.uk/-/media/uwe/documents/life/starbucks-menu.pdf)

3. Create a New AI Chatbot
1. From the Chatling dashboard, click **New → AI Chatbot**.  
2. Choose **Web** as the platform.  
3. Select **Start From Scratch**.  

4. Add Knowledge Base
1. In the left sidebar, go to **Knowledge Base**.  
2. Upload the following PDFs:  
3. Once uploaded, the assistant will be able to answer questions like:  
   - *“I’m looking for a latte, any recommendations?”*  
   - *“Do you have vegan options?”*
    
![Knowledge Base Upload](https://github.com/Reshmagvs/BrewBot_workshop/blob/main/ww1.png)  

5. **Go to the Builder Section**  
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

 

6. **Click on the Block Symbol**  
   - This lets you create your first building block.  

7. **Set up the First Text Block**  
   - Label the block as **`greeting`**  
   - Enter the following text:  

     ```
     Welcome to Starbucks!  
     I am Joanne, how can I assist you today?
     ```

8. **Capture User Response**  
   - Add a **Capture Response Text Block**  
   - Label it as **`capture user question`**  
   - Create a variable:  
     ```
     User_Query
     ```
     This will store the user’s input for later use.

9. **AI Response Block**  
   - Add an **AI Response Block**  
   - Configure it as follows:  
     - **Response Source:** Knowledge Base  
     - **Question Section:**  
       ```
       {User_Query}
       ```

10. **Intent Block**  
   - Add an **Intent Block** as " order status "  
   - In Chatling, an **intent** represents the underlying goal or purpose a user wants to achieve when they interact with the chatbot.  
   - Example intents:  
     - **Order Coffee**  
     - **Check Menu**  
     - **Store Timings**

 11. **Prompt for Order Number**  
    - Add a **Text Block** labeled **`prompt for order number`**  
    - Enter:  
      ```
      Please enter your order number to check the status.

      Example: 112
      ```

12. **Capture Order Number**  
    - Add a **Capture Response Block**  
    - Label it as **`capture and store the order number`**  
    - Create a variable:  
      ```
      Order_Number
      ```

13. **AI Order Number Validator**  
    - Add an **AI Response Block**  
    - Configure it as:  
      - **Response Source:** AI Model  
      - **Prompt:**  
        ```
        You are an order number validator. Your task is to evaluate whether a given order number 
        is valid and is in the correct format.

        The order number should meet the following criteria:
        - Contain numeric characters only
        - Must be less than four characters in length

        Here is the order number to evaluate:
        {Order_Number}

        Carefully examine the order number and determine if it meets all the specified criteria.

        If the order number is correct and meets all the criteria, output "1". 
        If the order number is incorrect or fails to meet any of the criteria, output "0".
        ```
      - **Save Response in Variable:**  
        ```
        order_num_validation
        ```

14. **Condition Block**  
    - Add a **Condition Block** labeled **`Valid Order Number?`**  
    - Condition:  
      ```
      If order_num_validation == 1
      ```

15. **Order Status / Invalid Response**  
    - Add two **Text Blocks**:  
      - **Label:** `order status`  
        ```
        Your order is being made and will be served soon, thank you for waiting patiently!
        ```
      - **Label:** `reprompt`  
        ```
        The order number "{Order_Number}" is invalid. 
        Please check and add a valid order number.
        ```

16. **Confirmation Step**  
    - Add a **Text Block** labeled **`confirmation`**  
    - Enter:  
      ```
      Is there anything else that I can assist you with?
      ```  
    - Add buttons: **Yes / No**

17. **End Chat**  
    - Add a **Text Block** labeled **`end chat`**  
    - Enter:  
      ```
      Thank you for chatting with us today! 
      If you have any questions, feel free to start a new chat!
      ```

---

## 👩‍💼 Human Agent Support Flow

18. **New Intent: Connect with Human Agent**  
    - Create a new intent: **Human Agent / Live Support**  

19. **Collect Order Details**  
    - Add a **Text Block** labeled **`collect order details`**  
      ```
      I can forward your message to our team and they will get in touch with you!
      ```
    - Add another **Text Block** labeled **`collect number`**  
      ```
      Please enter your number so we can reach out to you.
      ```
    - Add a **Capture Number Response Block**  
    - Add another **Text Block** labeled **`what is your query`**  
      ```
      What is your query?
      ```
    - Add a **Capture Text Response Block** with variable:  
      ```
      customer_query
      ```

20. **Support Confirmation**  
    - Add a **Text Block** labeled **`support confirmation`**  
      ```
      Your message has been sent to our Support team and we will be contacting you soon!
      ```

---

## 🧩 Final Step: Intent Matching

21. **Update Capture User Question Block**  
    - Go back to the **`capture user question`** block.  
    - Under **Match Intent Section**, add the following intents:  
      - **Human Agent / Live Support**  
      - **Order Status**  

---

✨ Congratulations! You’ve now built a **complete AI Coffee Assistant** with:  
- Greeting flow ☕  
- Order number validation ✅  
- Order status updates 📦  
- Human agent escalation 👩‍💼  

Your chatbot is ready to serve customers!
