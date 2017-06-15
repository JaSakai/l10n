# Usage of l10n tool for synchronizing translation resources between Sakai GitHub repository and Transifex.

1. First of all, you have to install transifex-client by following the procedures described in 'https://docs.transifex.com/client/installing-the-client'. Only installation step is needed, and you do not need to do 'Configuration' step described in that page.

1. Please download the latest sakai source code from GitHub by the following commands.
    ```
    git clone https://github.com/sakaiproject/sakai.git
    ```

1. After finishing download of all sakai source codes, please checkout all l10 source codes from this repository by following command. After that, you can see the folder 'l10n' on the top of the directory of the sakai sources (same directory level of 'access', 'alias', etc.).
    ```
   git clone https://github.com/JaSakai/l10n.git l10n
    ```

1. Please change the current directory to 'l10n' folder, and then run following command to setup the transifex for sakai. You may need to type username and password of Transifex.
    ```
   python tmx.py init
    ```

1. In the case of uploading translations to Transifex, please follow [5-i]. In the case of downloading translations from Transifex, please follow [5-ii].
    1. Please run following command to upload all localized resources to Transifex. Following command is an example for Japanese translation. Please change 'ja' to your language code.
        ```
        python tmx.py upload -u -l ja
        ```

    1. Please run following command to download all localized resources (ja: Japanese) from Transifex. If you want to download only reviewed resources, please add '-r' option. Following command is an example for Japanese translation. Please change 'ja' to your language code.
        ```
        python tmx.py download -u -l ja
        ```

After the step 5-ii, '.properties' files of sakai source codes are replaced with the translation done in Transifex. You need to do steps 1, 2, 3, and 4 only once, and you can skip these steps from the second trial.
