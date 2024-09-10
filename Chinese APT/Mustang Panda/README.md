# Mustang Panda APT Adversary Simulation

This is a simulation of attack by (Mustang Panda) APT group targeting government entities in Southeast Asia, the attack campaign was active from late September 2023, The attack chain starts with abuse of Visual Studio Code's reverse shell to execute arbitrary code and deliver additional payloads. To abuse Visual Studio Code for malicious purposes, an attacker can use the portable version of code.exe (the executable file for Visual Studio Code), or an already installed version of the software. By running the command code.exe tunnel, an attacker receives a link that requires them to log into GitHub with their own account, I relied on paloalto to figure out the details to make this simulation: https://unit42.paloaltonetworks.com/stately-taurus-abuses-vscode-southeast-asian-espionage/

![imageedit_3_4935006221](https://github.com/user-attachments/assets/8769d80f-3ddd-43d3-a6ff-9171af4e6acc)

This attack included several stages including redirect to a Visual Studio Code web environment that is connected to the compromised machine. They are then permitted to execute commands and scripts, and to create new files on the infected machine, Stately Taurus used this technique to deliver malware to infected environments, perform reconnaissance and exfiltrate sensitive data. To establish constant access to the reverse shell, the attacker created persistence for a script named (startcode.bat) using a scheduled task that is responsible for starting the shell.

1. Use Visual Studio Code's reverse shell to execute arbitrary code and deliver additional payloads.

![imageedit_2_2412587919](https://github.com/user-attachments/assets/ccc11e78-40c9-4573-bb3f-1854e0058a0d)

## The first stage (delivery technique)
In the beginning, I downloaded VS Code on Windows Target Machine, then I logged in to my GitHub account in the browser, and through it I logged in to my VScode account.

https://medium.com/@truvis.thornton/visual-studio-code-embedded-reverse-shell-and-how-to-block-create-sentinel-detection-and-add-e864ebafaf6d

![Screenshot from 2024-09-10 16-27-21](https://github.com/user-attachments/assets/4bb7cb38-9773-4440-85c6-e7d1a4aa8773)

_______________________________________________________________________________________________________________________

![Screenshot from 2024-09-10 16-27-50](https://github.com/user-attachments/assets/f691cecf-c1c5-4404-af2a-c89589c585db)

_______________________________________________________________________________________________________________________

To complete the process of linking the account you got with the VS code, I open CMD in Windows and write the command `code tunnel` so that the terminal gives us the link that we will use to complete the authentication process.

![Screenshot from 2024-09-10 16-45-42](https://github.com/user-attachments/assets/baaa7152-4263-4b4f-9e7e-694f2a42f52d)

_______________________________________________________________________________________________________________________


![Screenshot from 2024-09-10 16-48-09](https://github.com/user-attachments/assets/c7e2aeeb-762d-41dc-9363-21c9795d10ce)

_______________________________________________________________________________________________________________________



![Screenshot from 2024-09-10 16-49-02](https://github.com/user-attachments/assets/81e59367-3331-4ef0-b68b-abaa2e03695c)

_______________________________________________________________________________________________________________________


![Screenshot from 2024-09-10 16-49-23](https://github.com/user-attachments/assets/4e2fb722-876b-4585-974c-067615a8fc98)


_______________________________________________________________________________________________________________________

After that, the link will appear in the CMD, which i will use and open from the attacker browser to gain control over the victim VSCode through the attacker browser.

![photo_2024-09-10_18-12-27](https://github.com/user-attachments/assets/2a7236ba-bf11-4d56-b71a-346c509f165d)


_______________________________________________________________________________________________________________________

Now I have control over the target machine through my browser in Kali Linux.

![Screenshot from 2024-09-10 17-35-16](https://github.com/user-attachments/assets/c87e61d8-fbe6-4ef7-8b29-606aab7432fe)


_______________________________________________________________________________________________________________________





