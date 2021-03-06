﻿# A simple, cross platform, modularized captcha service system built on .NET Core 

Sample captcha service. An image with distorted text is shown to the user. The user has to input the text value in a textbox and submit. If the text input by the user is correct the service returns a pass else a fail.

## Visual Studio 2019

#### Prerequisites

Before starting to run the solution locally, you need to ensure you have installed the right tools on your machine. In particular,since this solution uses ASP.NET Core 3.0, you need to check if you have installed the .NET Core 3.0 SDK by typing the following command in a terminal window: `dotnet version`.

You should get as a result the value 3.0.100 or above. If don't, you should [download .NET Core 3.0 SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0) and install it on your machine.

If you are going to use Visual Studio, be aware that you need to use [Visual Studio 2019 16.3](https://devblogs.microsoft.com/visualstudio/dot-net-core-support-in-visual-studio-2019-version-16-3/) or [Visual Studio for Mac 8.3](https://devblogs.microsoft.com/visualstudio/visual-studio-2019-for-mac-version-8-3/) or above.  

#### Steps to run

##### Using .NET Core CLI

- Clone the repository
- In the terminal windows move to the *service\SimpleCaptcha.API* folder
- run command `dotnet run`

##### Using Visual Studio

- Clone the repository
- Move to folder *service*
- Open *SimpleCaptcha.API.sln* file
- Hit *Ctlr+F5*

If everything is okay, open a terminal window and type the following command:

1. To generate captcha
`curl --insecure https://localhost:5001/api/captcha/generate`

![](images/Get_Captcha.PNG)

2. To validate captcha
`curl --insecure -X POST -d "{\"captchaCode\":\"AB1D\", \"userInput\":\"ABD\"}" -H "Content-Type: application/json" https://localhost:5001/api/captcha/validate`

![](images/Valid_Captcha.PNG)

![](images/Invalid_Captcha.PNG)

**Note:** Service returns the captcha as a captcha byte stream