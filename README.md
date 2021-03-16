# Retirement_Portfolio_Chatbot
This is my chatbot created to help you assign a risk level to your retirement portfolio (AWS &amp; Python based)

I used the AWS Lex Bot and the AWS Lambda to incorporate python code.

## Option 1: Robo Advisor for Retirement Plans

![Robot](robot.jpg)

*Photo by [Alex Knight](https://www.pexels.com/@alex-knight-1272316?utm_content=attributionCopyText&utm_medium=referral&utm_source=pexels) from [Pexels](https://www.pexels.com/photo/high-angle-photo-of-robot-2599244/?utm_content=attributionCopyText&utm_medium=referral&utm_source=pexels) | [Free License](https://www.pexels.com/photo-license/)*

### Background

This story was that I was hired as a digital transformation consultant by one of the most prominent retirement plan providers in the country; they wanted to increase their client portfolio, especially by engaging young people. Since machine learning and NLP are disrupting finance to improve customer experience, I decided to create a robo advisor that could be used by customers or potential new customers to get investment portfolio recommendations for retirement.

I combined my new Amazon Web Services skills with my Python prowess to create a bot that recommends an investment portfolio for a retirement plan.

I accomplished these tasks:

1. **[Initialized Robo Advisor Configuration:](#Initial-Robo-Advisor-Configuration)** Defined an Amazon Lex bot with a single intent that establishes a conversation about the requirements to suggest an investment portfolio for retirement.

2. **[Built and Test the Robo Advisor](#Build-and-Test-the-Robo-Advisor):** Made sure that your bot is working and responding accurately along with the conversation with the user, by building and testing it.

3. **[Enhanced the Robo Advisor with an Amazon Lambda Function:](#Enhance-the-Robo-Advisor-with-an-Amazon-Lambda-Function)** Created an Amazon Lambda function that validates the user's input and returns the investment portfolio recommendation. This task includes testing the Amazon Lambda function and making the integration with the bot.

---

### Files

* [lambda_function.py](Starter_Files/lambda_function.py)
* [correct_dialog.txt](Test_Cases/correct_dialog.txt)
* [age_error.txt](Test_Cases/age_error.txt)
* [incorrect_amount_error.txt](Test_Cases/incorrect_amount_error.txt)
* [negative_age_error.txt](Test_Cases/negative_age_error.txt)

---

### Instructions

#### Initial Robo Advisor Configuration

Signed in into your AWS Management Console and [create a new custom Amazon Lex bot](https://console.aws.amazon.com/lex/home).

Created the `RecommendPortfolio` intent, and configure some sample utterances as follows (you can add more utterances as you wish):

* I want to save money for my retirement
* I'm ​`{age}​` and I would like to invest for my retirement
* I'm `​{age}​` and I want to invest for my retirement
* I want the best option to invest for my retirement
* I'm worried about my retirement
* I want to invest for my retirement
* I would like to invest for my retirement

This bot will use four slots, three using built-in types and one custom slot named `riskLevel`. Define the three initial slots as follows:


| Name             | Slot Type            | Prompt                                                                    |
| ---------------- | -------------------- | ------------------------------------------------------------------------- |
| firstName        | AMAZON.US_FIRST_NAME | Thank you for trusting me to help, could you please give me your name? |
| age              | AMAZON.NUMBER        | How old are you?                                                          |
| investmentAmount | AMAZON.NUMBER        | How much do you want to invest?                                           |

To format the response cards for the intent, click on the gear icon next to the intent as seen in the image below:

![gear_icon](gear_icon.png)

Next, input the following data in the resulting display window:

* **Prompt:** What level of investment risk would you like to take?
* **Maximum number of retries:** 2
* **Prompt response cards:** 4

Configure the response cards for the `riskLevel` slot as is shown bellow:

| Card 1                              | Card 2                              |
| ----------------------------------- | ----------------------------------- |
| ![Card 1 sample](Images/card1.png)  | ![Card 2 sample](Images/card2.png)  |

| Card 3                              | Card 4                              |
| ----------------------------------- | ----------------------------------- |
| ![Card 3 sample](Images/card3.png)  | ![Card 4 sample](Images/card4.png)  |


# HERE IS THE BOT!

![The BOT](Tory_AWSlex_Chatbot_RetirementPorfolio_Recommendation.mov)



