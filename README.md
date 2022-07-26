
# Bank of Python

Live version available here: [Bank of Python](https://bank-of-python.herokuapp.com/)

## About the Bank of Python

The Bank of Python is a banking application that allows customers to open an account to deposit with the bank. They can change their PIN and also make a withdrawal, should they have the requested funds available in their account.

![Screenshot 2022-07-26 at 15 55 04](https://user-images.githubusercontent.com/98256205/181040933-0c0e34be-bd76-49ca-babb-fce91cbe972b.png)

## Table of Contents
* Design
* Features
* Database
* Testing
* Unfixed Bug
* Technologies Used
* Deployment
* Libraries
* Acknowledgement

## Design
### Wireframe
Lucid app was used to plan the logic for this project. Below is a screenshot of the logic.

![Flowcharts - Algorithm flowchart example (1)](https://user-images.githubusercontent.com/98256205/181049018-40b20bf3-34fe-4d77-b31f-7bf2a5a76c16.jpeg)

## Features
### Welcome Screen

Upon startup the program display a welcome screen. This includes a logo, options to perform 3 banking actions and a 4th option which terminates the program.

### Create accounts

This option allows the user to enter their name, a PIN and a balance to be deposited. A unique account number is then created and assigned to the account after the details are pushed to the database. This account number is then shared with the user who will need it to access the account in future. 

![Screenshot 2022-07-26 at 16 49 23](https://user-images.githubusercontent.com/98256205/181052281-b8c54d8c-aa45-45a3-b493-25fd37c6b819.png)

![Screenshot 2022-07-26 at 16 49 40](https://user-images.githubusercontent.com/98256205/181052316-43ebbeee-2899-484a-9a5e-6b593ccf8d2d.png)

![Screenshot 2022-07-26 at 16 50 01](https://user-images.githubusercontent.com/98256205/181052370-4bdadb93-0323-4b4d-9434-c4158859982c.png)

![Screenshot 2022-07-26 at 16 50 10](https://user-images.githubusercontent.com/98256205/181052382-3182bb60-ea70-4a74-ab27-87a69aff3f46.png)

### Change PIN

This option allows the user to change their PIN. They must provide their account number and current PIN. The program will then ask them to enter the new PIN 2 times to be sure that the new PINS match.

![Screenshot 2022-07-26 at 16 54 16](https://user-images.githubusercontent.com/98256205/181053476-51ec6521-130e-43ed-a4be-1a9d68f533a5.png)

![Screenshot 2022-07-26 at 16 54 32](https://user-images.githubusercontent.com/98256205/181053496-ff5d3d59-9059-4302-9a1c-5006e44dad66.png)

![Screenshot 2022-07-26 at 16 54 43](https://user-images.githubusercontent.com/98256205/181053509-b46a1d8a-5510-4f9f-bdbf-bc1f60f77777.png)

![Screenshot 2022-07-26 at 16 54 57](https://user-images.githubusercontent.com/98256205/181053522-893c86f9-ea9b-416e-a430-206797783d78.png)

![Screenshot 2022-07-26 at 16 55 02](https://user-images.githubusercontent.com/98256205/181053538-edc6e27d-660e-4d8c-a3d9-69c17a338299.png)

### Withdrawal

This option allows the user to make a withdrawal. It requires that the user withdraw a multiple of 10 and that they have the available balance.

![Screenshot 2022-07-26 at 16 58 31](https://user-images.githubusercontent.com/98256205/181054311-bf78437a-5f1a-4879-bc09-110498d33a45.png)

![Screenshot 2022-07-26 at 16 58 45](https://user-images.githubusercontent.com/98256205/181054350-8baefb94-2f70-44c8-a0bd-86e9bb4ff627.png)

![Screenshot 2022-07-26 at 16 58 50](https://user-images.githubusercontent.com/98256205/181054372-8ba20d19-3aa8-45fb-a9ea-87db91aaab53.png)

![Screenshot 2022-07-26 at 16 59 04](https://user-images.githubusercontent.com/98256205/181054389-c0c6d492-f519-4639-ba29-7f74002b5f12.png)

![Screenshot 2022-07-26 at 16 59 32](https://user-images.githubusercontent.com/98256205/181054405-d2040615-65e8-448a-8272-13e61afbf91e.png)

### Exit Program

This option terminates the program.

## Database

The Google Sheets API was utilised to store customer account information. It holds the name, PIN and balance.

![Screenshot 2022-07-26 at 17 07 01](https://user-images.githubusercontent.com/98256205/181056128-12380915-501a-40f8-aed8-b4b106e0f458.png)

## Testing

To test this program I have visited every possible outcome of the program. I have repeated this process at various stages to ensure that the intended responses are provided. It has proved to be essential in locating bugs and optimising design. I also put the code through the PEP8 validator to check for conformity. All errors were taken on board and the code was refactored to remove them. I used to AutoPEP8 to speed up the refactoring process although some manual work was still needed to complete the process. I passed the deployed app around to a few fellow developers and asked them to break it and give feedback. The extra eyes gave me insight into some error handling cases that I had missed.

![Screenshot 2022-07-27 at 12 28 21](https://user-images.githubusercontent.com/98256205/181238141-dd2c8339-817e-41bb-9636-5274f6b6e275.png)

## Bugs 

* There was a bug that would not let the "Exit program" option to run properly when returning from the "Create Account" menu option. I couldd't seem to figure it out so had to get creative. Since it was the main menu I was able to install a library and use it to reset the program at that point giving us a clean start. This didn't fix the original bug but it regained the function of the program without affecting user experience so it was a satisfactory patch.
* There were a lot of ways to crash this program with empty inputs or unexpected inputs. I systematically found and closed every one of these errors. I used try/except blocks to handle most of the errors.

## Deployment

This app was deployed to Heroku. Below are the steps taken for its deployment

* Create and account and log in to heroku
* Create a new app
* Go to settings option
* Add 'key/value' pairs. First key is CREDS and its value is copied from creds.json file on gitpod. The second key is PORT with 8000 as its value
* Add build pack. Add python first and then nodejs second in that order.
* Go to the top of the page, then select 'deploy tab' and then choose 'Github deployment'.
* Click to navigate to the deployed project

To clone the project, navigate to the repository button on the GitHub and select zip or open with Github desktop. After that, copy and paste the link to your git terminal by clicking GitHub CLI and the copy button in the code dropdown menu.

## Libraries

The following libraries were utilised in building this project

* Gspread to enable the opening, accessing and reading of googlesheet data.
* Credentials they serve as unique identifiers required to access my API.
* Time was used to create a timely flow of event as the customer performs transactions.
* Pyfiglet was used to create the ASCII art headers.
* Subprocess was used to cleanly restart the program due to a bug that I couldn't find. 
* OS was used to clear the terminal during the programs running.

## Acknowledgments

* Ger Kelly for helping me to test the app and finding a bug I had missed. Also for suggesting Pyfiglet.
* My mentor, Martina Terlevic for keeping me on the right track. 
* Gaff for suggesting AutoPEP8 and saving me from manual refactoring.
* gozygreg (on GitHub) whose readme was my template for this one. 







