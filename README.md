# BASIC - How to setup for hosting on GitHub Pages

In order to follow this tutorial, first fork this repository, and then clone your newly forked copy locally.

First, you'll need to edit the `addon.xml` file within the `/repository.example` folder with your chosen add-on ID, a version number, and your username (or whatever you'd like) for `provider`, as seen on line 2:

```XML
<addon id="ADDON_ID_HERE" name="REPO_NAME_HERE" version="VERSION_NUMBER_HERE" provider-name="YOUR_USERNAME_HERE">
```

You also need to replace `YOUR_USERNAME_HERE` and `REPOSITORY_NAME_HERE` with your GitHub username and this repository's name, respectively, as seen on lines 5-7:

```XML
<info compressed="false">https://raw.githubusercontent.com/YOUR_USERNAME_HERE/REPOSITORY_NAME_HERE/master/zips/addons.xml</info>
<checksum>https://raw.githubusercontent.com/YOUR_USERNAME_HERE/REPOSITORY_NAME_HERE/master/zips/addons.xml.md5</checksum>
<datadir zip="true">https://raw.githubusercontent.com/YOUR_USERNAME_HERE/REPOSITORY_NAME_HERE/master/zips/</datadir>
```

You should also change the summary and description of your repository, as seen on lines 11-12:

```XML
<summary>REPO_NAME_HERE</summary>
<description>DESCRIPTION OF YOUR REPO HERE</description>
```

While not required, it is also recommended to replace `icon.png` and `fanart.jpg` in the `/repository.example` folder with art relevant to your repository or the add-ons contained within. `icon.png` should be 512x512 px, and `fanart.jpg` should be 1920x1080 px, or a similar ratio.

To build the repository, first rename the `/repository.example` folder to match whatever add-on ID you chose earlier. Place the add-on source folders for whichever add-ons you'd like to be contained in your Kodi repo in the main folder of this repository, and run `_repo_xml_generator.py`. 

This will create zips of all of the desired add-ons, and place them in the `zips` folder, along with a generated `addons.xml` and `addons.xml.md5`. Copy the zip file of your repository, located at `/zips/ADDON_ID_HERE/ADDON_ID_HERE-VERSION_NUMBER_HERE.zip`,
and paste it into the `/repo` folder.

Inside the `/repo` folder, edit the link inside `index.html` to reflect your add-on's filename, as seen on line 1:

```HTML
<a href="ADDON_ID_HERE-VERSION_NUMBER_HERE.zip">ADDON_ID_HERE-VERSION_NUMBER_HERE.zip</a>
```

After committing and pushing these changes to your repo, go to the "Settings" section for this repository on GitHub. In the first box, labeled "Repository name", change your repository's name. Generally, GitHub Pages repositories are named `YOUR_USERNAME_HERE.github.io`,  but it can be whatever you'd like.
Next, scroll down to the "GitHub Pages" section, choose the `master` branch as the source, and click "Save".

After that, you should be all done!

If you named this repository `YOUR_USERNAME_HERE.github.io`, your file manager source will be:

`https://YOUR_USERNAME_HERE.github.io/repo/`

And if you named it something else, it will be:

`https://YOUR_USERNAME_HERE.github.io/REPOSITORY_NAME_HERE/repo/`

# ADVANCED - How to set up for hosting without GitHub Pages

If you want to host your Kodi repo on a different host besides GitHub Pages, simply download this repository as a `.zip`, and unzip it , rather than forking and cloning it. Continue to follow the rest of the setup procedure, except for the setting up of GitHub Pages. The only differences will be in your `addon.xml` file (lines 5-7), as it will need to reference yourhost, rather than GitHub:

```XML
<info compressed="false">https://YOUR_HOST_URL_HERE/zips/addons.xml</info>
<checksum>https://YOUR_HOST_URL_HERE/zips/addons.xml.md5</checksum>
<datadir zip="true">https://YOUR_HOST_URL_HERE/zips/</datadir>
```

And upload the contents of this repository to your host. It is **very important** that `YOUR_HOST_URL_HERE` is the URL to *this* folder.

After doing so, your file manager source will be:

`https://YOUR_HOST_URL_HERE/repo/`

# BASIC - Как настроить хостинг на GitHub Pages

Чтобы следовать этому руководству, сначала создайте вилку этого репозитория, а затем локально клонируйте созданную копию.

Во-первых, вам нужно отредактировать файл `addon.xml` в папке` / repository.example`, указав выбранный вами идентификатор надстройки, номер версии и ваше имя пользователя (или что угодно) для `provider `, как показано в строке 2:

``` XML
<addon id = "ADDON_ID_HERE" name = "REPO_NAME_HERE" version = "VERSION_NUMBER_HERE" provider-name = "YOUR_USERNAME_HERE">
```

Вам также необходимо заменить `YOUR_USERNAME_HERE` и` REPOSITORY_NAME_HERE` на ваше имя пользователя GitHub и имя этого репозитория, соответственно, как показано в строках 5-7:

``` XML
<info compressed = "false"> https://raw.githubusercontent.com/YOUR_USERNAME_HERE/REPOSITORY_NAME_HERE/master/zips/addons.xml </info>
<checksum> https://raw.githubusercontent.com/YOUR_USERNAME_HERE/REPOSITORY_NAME_HERE/master/zips/addons.xml.md5 </checksum>
<datadir zip = "true"> https://raw.githubusercontent.com/YOUR_USERNAME_HERE/REPOSITORY_NAME_HERE/master/zips/ </datadir>
```

Вам также следует изменить сводку и описание вашего репозитория, как показано в строках 11-12:

``` XML
<summary> REPO_NAME_HERE </summary>
<description> ОПИСАНИЕ ВАШЕГО РЕПО ЗДЕСЬ </description>
```

Хотя это и не обязательно, рекомендуется также заменить `icon.png` и` fanart.jpg` в папке `/ repository.example` изображениями, относящимися к вашему репозиторию или надстройкам, содержащимся в нем. `icon.png` должен иметь размер 512x512 пикселей, а` fanart.jpg` должен иметь размер 1920x1080 пикселей или аналогичное соотношение.

Чтобы создать репозиторий, сначала переименуйте папку `/ repository.example`, чтобы она соответствовала идентификатору надстройки, который вы выбрали ранее. Поместите исходные папки надстроек для любых надстроек, которые вы хотите включить в репозиторий Kodi, в основную папку этого репозитория и запустите `_repo_xml_generator.py`.

Это создаст zip-архивы всех желаемых надстроек и поместит их в папку `zips` вместе с сгенерированными` addons.xml` и `addons.xml.md5`. Скопируйте zip-файл вашего репозитория, расположенный в `/ zips / ADDON_ID_HERE / ADDON_ID_HERE-VERSION_NUMBER_HERE.zip`,
и вставьте его в папку `/ repo`.

Внутри папки `/ repo` отредактируйте ссылку внутри` index.html`, чтобы отразить имя файла вашей надстройки, как показано в строке 1:

``` HTML
<a href="ADDON_ID_HERE-VERSION_NUMBER_HERE.zip"> ADDON_ID_HERE-VERSION_NUMBER_HERE.zip </a>
```

После фиксации и отправки этих изменений в репозиторий перейдите в раздел «Настройки» этого репозитория на GitHub. В первом поле с надписью «Имя репозитория» измените имя репозитория. Обычно репозитории GitHub Pages называются `YOUR_USERNAME_HERE.github.io`, но это может быть что угодно.
Затем прокрутите вниз до раздела «GitHub Pages», выберите ветку `master` в качестве источника и нажмите« Сохранить ».

После этого все должно быть готово!

Если вы назвали этот репозиторий `YOUR_USERNAME_HERE.github.io`, источником вашего файлового менеджера будет:

`https: // ВАШЕ ИМЯ_ПОЛЬЗОВАТЕЛЯ_ ЗДЕСЬ.github.io / repo /`

И если вы назвали его как-нибудь иначе, это будет:

`https: // ВАШЕ ИМЯ_ПОЛЬЗОВАТЕЛЯ_HERE.github.io / REPOSITORY_NAME_HERE / repo /`

# ADVANCED - Как настроить хостинг без GitHub Pages

Если вы хотите разместить свое репозиторий Kodi на другом хосте, кроме GitHub Pages, просто загрузите этот репозиторий как .zip и разархивируйте его, а не разветвляйте и клонируйте. Продолжайте следовать остальной части процедуры настройки, за исключением настройки GitHub Pages. Единственные различия будут в вашем файле `addon.xml` (строки 5-7), так как он должен будет ссылаться на ваш хост, а не на GitHub:

``` XML
<info compressed = "false"> https: //YOUR_HOST_URL_HERE/zips/addons.xml </info>
<checksum> https: //YOUR_HOST_URL_HERE/zips/addons.xml.md5 </checksum>
<datadir zip = "true"> https: // YOUR_HOST_URL_HERE / zips / </datadir>
```

И загрузите содержимое этого репозитория на свой хост. ** очень важно **, чтобы `YOUR_HOST_URL_HERE` был URL-адресом * этой * папки.

После этого исходный код вашего файлового менеджера будет:

`https: // YOUR_HOST_URL_HERE / repo /`




