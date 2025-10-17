# How I Created My E-Portfolio

## Introduction

As part of the *Tools and Techs for Business Analytics* class in the Supply Chain Analytics Master, I created my e-portfolio on GitHub Pages to highlight my achievements and experiences. To build it, I used **GitHub**, a *"cloud-based service for storing and sharing source code"*, to create the repository hosting my e-portfolio, and **VSCode**, a code editor, to develop the content. Below are the detailed steps I followed to create my e-portfolio. 

## Step 1 - Create a New Repository on GitHub
1. Sign in to your GitHub account

2. From the *Home* page click **New** (green button)

3. Enter the repository name as follow: `<username>.github.io`, where `<username>` is your GitHub username

4. In the *Configuration* section : 
    - Choose visibility: **Public**
    - Add README: **On**
    - Add license: **MIT License**

5. Click **Create repository**

6. Verify the GitHub Pages settings: 
    - Under your repository name, click **Setting**
    - In the sidebar, under *Code and automation*, click **Pages**
    - Under *Build and deployment*, under *Source*, select **Deploy from a branch** 
    - Under *Branch*,  make sure to select **main** for the branch, and **/ (root)** for the folder 
    - Click **Save** if necessary

You can also find a more visual explanation of creating GitHub Pages [here](https://docs.github.com/en/pages/quickstart).

## Step 2 - Clone Your Repository 
1. On GitHub, in the repository you just created, click **Code** (green button)

2. Copy the web URL of your repository

3. Open *GitHub Desktop* and select **File > Clone Repository** 
    - Select the **URL** tab and **paste** the web URL of your repository
    - In the *Local Path* section, choose where you want to save the repository on your device
    - Click **Clone**

4. Verify that the repository appears in the folder you selected, and contains the **README.md** and **LICENSE** files

## Step 3 - Upload The Theme to Your Repository
In my case, I uploaded a pre-made theme called *minimal*. To do so, I *forked* (copied) an existing repository and added it to my own. 
1. Click the following link: [https://github.com/pages-themes/minimal](https://github.com/pages-themes/minimal)

2. Click **Code** (green button), then select **Download ZIP**

3. If necessary, unzip the downloaded folder, and move it into your cloned repository folder on your device 

4. In *GitHub Desktop*: 
    - Ensure the **Current Repository** (top-left) is set to `<username>.github.io`
    - In the **Summary** box, briefly describe the changes you've made
    - Click **Commit to main** (blue button)
    - At the top, click **Push origin** 

5. Go back to your repository on the GitHub website and check that the new folder named **"minimal-master"** is there

## Step 4 - VSCode 
Let's start with opening your repository using VSCode. 
1. Open *VSCode App*

2. In **File** > **Open Folder** > **`<username>.github.io`** 

3. On the left sidebar, you should see your repository with the folder and files it contains

## Step 5 - Set Up The Theme to Your Repository
1. In *VSCode*, inside the "minimal-master" folder, find the **README.md** file and open it

2. Follow the instructions in the "**Usage**" and "**Configuration Variables**" sections of the **README.md** file to set up the theme: 
    - Move the files `_config.yml` and `Gemfile`(optional) to your root repository - your `<username>.github.io` folder
    - Open the `_config.yml` file in VSCode and: 
        - Modify the **`title`** of your e-portfolio
        - Add a **`description`** to your e-portfolio
        - Set **`show_downloads`** to either `"true"` or `"false"` to indicate whether you want to provide a download URL
        - If you have one, enter your **`google_analytics`** tracking ID 

You can see  an example of `title`, `description`, and `show_downloads` setup [here](../assets/img/config.yml_updated.png). 

3. Save your changes

4. Open *GitHub Desktop*, add a brief **summary**, click **Commit to main**, then click **Push origin**. This will ensure your repository is updated online 

5. Visit your e-portfolio at `<username>.github.io` to check the theme works correctly

## Step 6 - Upload Your Picture
You can replace the logo.png in the *img* subfolder of the *assets* folder with your headshot. 
1. Move the `assets` folder to your root repository folder

2. Choose your **headshot** and save it to the `img` subfolder using the same file name as the existing one (`logo.png`)

3. Replace the original image with your own

4. Save your changes

5. Open *GitHub Desktop*, add a brief **summary**, click **Commit to main**, then click **Push origin**

6. Visit your e-portfolio at `<username>.github.io` to confirm the picture appears correctly

## Step 7 - Develop The Content of Your E-Portofolio
The **`index.md`** file is where the main content of your e-portfolio is developed. 
1.  Move the **`index.md`** file to your **root repository** folder

2. Open the **`index.md`** file in VSCode

3. Rewrite it with your own information using at least five different types of markdown commands
    - You can follow a regular resume structure to organize your `index.md` file
    - Find an example using different types of markdown commands [here](../assets/img/index.md_updated.png)

4. Save your changes

After moving all the necessary folders and files, your root repository folder should be organized like [this](../assets/img/root_folder_org.png).

## Step 8 - Final Commit to Your GitHub Repository
1. Open *GitHub Desktop*, add a brief **summary**, click **Commit to main**, then click **Push origin**

2. Verify your e-portfolio deployment: 
    - On *GitHub*, navigate to the **Actions** tab and verify that *pages build and deployment* shows green check marks
    - Visit your e-portfolio page at `<username>.github.io` to confirm the updates appear correctly 

Your final e-portfolio should look like [this](../assets/img/final_eportfolio.png). It shows all the changes made in the previous folders and files, from the title and escription to the headshot and main content. 

### References
- GitHub. "Quickstart for GitHub Pages". Retrieved October 16th, 2025. [https://docs.github.com/en/pages/quickstart](https://docs.github.com/en/pages/quickstart)
- Visual Studio Code. "Working with GitHub in VS Code". Retrieved October 16th, 2025. [https://code.visualstudio.com/docs/sourcecontrol/github](https://code.visualstudio.com/docs/sourcecontrol/github)
