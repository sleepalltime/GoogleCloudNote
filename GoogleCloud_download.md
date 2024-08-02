# Google Cloud 批量下載筆記

---

## 安裝Google Cloud CLI

> **點擊以下連結取得
>https://cloud.google.com/sdk/docs/install-sdk?hl=zh-cn**

## 安裝Google Cloud CLI 後

### 設定配置

在安裝完成後會自動開啟命令提示符（CMD），並運行以下

```
Welcome to the Google Cloud CLI! Run "gcloud -h" to get the list of available commands.
---
Welcome! This command will take you through the configuration of gcloud.

Settings from your current configuration [default] are:
accessibility:
  screen_reader: 'False'
core:
  disable_usage_reporting: 'True'

Pick configuration to use:
 [1] Re-initialize this configuration [default] with new settings
 [2] Create a new configuration    
Please enter your numeric choice:
```

根據上面
> Pick configuration to use:  //選擇配置
> [1] Re-initialize this configuration [default] with new settings //重新初始化[default]的設定
> [2] Create a new configuration  //創建新配置

這邊我選擇創建新配置，所以在`Please enter your numeric choice:`後輸入2

若是已有配置，會多一個**切换到另一個配置並重新初始化**的選項[3]

```
Pick configuration to use:
 [1] Re-initialize this configuration [configuration-test] with new settings
 [2] Create a new configuration
 [3] Switch to and re-initialize existing configuration: [default]
Please enter your numeric choice:
```

---

#### 選擇配置到哪個帳號
```
Enter configuration name. Names start with a lower case letter and contain only lower case letters a-z, digits 0-9, and
hyphens '-':  configuration2-test
Your current configuration has been set to: [configuration2-test]

You can skip diagnostics next time by using the following flag:
  gcloud init --skip-diagnostics

Network diagnostic detects and fixes local network connection issues.
Checking network connection...done.
Reachability Check passed.
Network diagnostic passed (1/1 checks passed).

Choose the account you want to use for this configuration.
To use a federated user account, exit this command and sign in to the gcloud CLI with your login configuration file,
then run this command again.

Select an account:
 [1] info@aifunschool@gmail.com
 [2] Sign in with a new Google Account
Please enter your numeric choice:
```

根據上面
> Enter configuration name. Names start with a lower case letter and contain only lower case letters a-z, digits 0-9, and hyphens '-':  configuration2-test //在:後面輸入配置名稱，這裡我取名為**configuration2-test**

> Select an account: //選擇要建立配置的帳號
> [1] info@aifunschool@gmail.com  //現有的帳號
> [2] Sign in with a new Google Account  //創建新帳號

這邊我選擇使用現有的帳號，所以在`Please enter your numeric choice:`後輸入1

> 若想創建新帳號可以參考以下連結的教學
> https://kejyuntw.gitbooks.io/google-cloud-platform-learning-notes/content/gcloud/gcloud-README.html

---

#### 選擇配置到哪個專案
```
Please enter your numeric choice:  1

You are signed in as: [info.aifunschool@gmail.com].

Pick cloud project to use:
 [1] myplaygames@392212--
 [2] temposlash@cd8--
 [3] Enter a project ID
 [4] Create a new project
Please enter numeric choice or text value (must exactly match list item):
```
根據上面
> Pick cloud project to use:  //選擇要使用的雲端專案
> [1] myplaygames@392212--
> [2] temposlash@cd8--
> [3] Enter a project ID    //輸入專案ID
> [4] Create a new project  //創建新專案

這邊選擇使用[1]，所以在`Please enter numeric choice or text value (must exactly match list item):`後輸入1

---

#### 選擇配置區域
```
Your current project has been set to: [myplaygames@392212--].

Do you want to configure a default Compute Region and Zone? (Y/n)?  Y

Which Google Compute Engine zone would you like to use as project default?
If you do not specify a zone via a command line flag while working with Compute Engine resources, the default is
assumed.
 [1] us-east1-b
 [2] us-east1-c
 [3] us-east1-d
 [4] us-east4-c
 [5] us-east4-b
 [6] us-east4-a
 [7] us-central1-c
 [8] us-central1-a
 [9] us-central1-f
 [10] us-central1-b
 [11] us-west1-b
 [12] us-west1-c
 [13] us-west1-a
 [14] europe-west4-a
 [15] europe-west4-b
 [16] europe-west4-c
 [17] europe-west1-b
 [18] europe-west1-d
 [19] europe-west1-c
 [20] europe-west3-c
 [21] europe-west3-a
 [22] europe-west3-b
 [23] europe-west2-c
 [24] europe-west2-b
 [25] europe-west2-a
 [26] asia-east1-b
 [27] asia-east1-a
 [28] asia-east1-c
 [29] asia-southeast1-b
 [30] asia-southeast1-a
 [31] asia-southeast1-c
 [32] asia-northeast1-b
 [33] asia-northeast1-c
 [34] asia-northeast1-a
 [35] asia-south1-c
 [36] asia-south1-b
 [37] asia-south1-a
 [38] australia-southeast1-b
 [39] australia-southeast1-c
 [40] australia-southeast1-a
 [41] southamerica-east1-b
 [42] southamerica-east1-c
 [43] southamerica-east1-a
 [44] africa-south1-a
 [45] africa-south1-b
 [46] africa-south1-c
 [47] asia-east2-a
 [48] asia-east2-b
 [49] asia-east2-c
 [50] asia-northeast2-a
Did not print [72] options.
Too many options [122]. Enter "list" at prompt to print choices fully.
Please enter numeric choice or text value (must exactly match list item):
```

根據上面
> Your current project has been set to: [myplaygames@392212--].
> Do you want to configure a default Compute Region and Zone? (Y/n)?  Y

將配置設定在所選的專案中後，會要求配置區域，**這裡一定要輸入Y**
之後將區域配置在`[26] asia-east1-b`，所以在`Please enter numeric choice or text value (must exactly match list item):`後輸入26

```
Please enter numeric choice or text value (must exactly match list item):  26

Your project default Compute Engine zone has been set to [asia-east1-b].
You can change it by running [gcloud config set compute/zone NAME].

Your project default Compute Engine region has been set to [asia-east1].
You can change it by running [gcloud config set compute/region NAME].

The Google Cloud CLI is configured and ready to use!

* Commands that require authentication will use info@aifunschool@gmail.com by default
* Commands will reference project `myplaygames@392212--` by default
* Compute Engine commands will use region `asia-east1` by default
* Compute Engine commands will use zone `asia-east1-b` by default

Run `gcloud help config` to learn how to change individual settings

This gcloud configuration is called [configuration2-test]. You can create additional configurations if you work with multiple accounts and/or projects.
Run `gcloud topic configurations` to learn more.

Some things to try next:

* Run `gcloud --help` to see the Cloud Platform services you can interact with. And run `gcloud help COMMAND` to get help on any gcloud command.
* Run `gcloud topic --help` to learn about advanced features of the CLI like arg files and output formatting
* Run `gcloud cheat-sheet` to see a roster of go-to `gcloud` commands.

C:\WINDOWS\System32>
```
**如此就可以完成配置**

完成配置後，若之後想下載檔案直接執行以下下載指令即可

---

### 下載指令格式

```
C:\WINDOWS\System32>
```

當前資料夾**不是**目標路徑

* 下載資料夾
  * `gsutil cp -r gs://download-file-area/Preschool/Builds/LocalVersion/* H:\新增資料夾\`
  * `gsutil -m cp -r "gs://aifunupdata/科普島影片" "H:\新增資料夾"`

* 下載多個檔案 
  * `gsutil -m cp "gs://aifunupdata/科普島影片/動物的分類.webm" "gs://aifunupdata/科普島影片/松鼠測試影片.webm" H:\新增資料夾\`

> "H:\新增資料夾"為設定的目標路徑，可自行更改

```
cd /d H:\新增資料夾(設定的目標路徑)
```

將資料夾導航到目標資料夾，所以當前資料夾**是**目標路徑

* 下載資料夾
  * `gsutil cp -r gs://download-file-area/Preschool/Builds/LocalVersion/ .
`
  * `gsutil -m cp -r "gs://aifunupdata/科普島影片" .
`

* 下載多個檔案
  * `gsutil -m cp "gs://aifunupdata/科普島影片/動物的分類.webm" "gs://aifunupdata/科普島影片/松鼠測試影片.webm" .
`

> #### 下載指令解釋

範例1:
```
gsutil -m cp -r "gs://aifunupdata/科普島影片" "H:\新增資料夾"
```

* -m：啟用多線程處理以加快複製速度
* cp：複製指令
* -r：遞歸複製整個資料夾
* `"gs://aifunupdata/科普島影片"` >>源資料夾 URL (可替換成不同URL)
* `"H:\新增資料夾"` >>目標路徑

範例2:
```
gsutil -m cp "gs://aifunupdata/科普島影片/動物的分類.webm" "gs://aifunupdata/科普島影片/松鼠測試影片.webm" .
```

* -m：啟用多線程處理以加快複製速度
* cp：複製指令
* `"gs://aifunupdata/科普島影片/動物的分類.webm"` >>源 URL
* `"gs://aifunupdata/科普島影片/松鼠測試影片.webm"` >>另一個源 URL
* `.` >>當前資料夾
若要下載到當前資料夾**此 . 不可以**刪除

---

## gsutil 指令整理

**初始化 gcloud 設定**

若在安裝Google Cloud CLI後沒有自動開啟命令提示符（CMD），也可以手動開啟（CMD）並輸入下面指令
```
gcloud init
```

---

**跳過診斷**
```
gcloud init --skip-diagnostics
```

---

**帳號登入**
```
gcloud auth login
```

---

**檢查目前的 Google Cloud CLI 版本**
```
gsutil version
```

---

**更新 Google Cloud CLI 版本**
```
gcloud components update
```

###

> **更多gcloud config 設定配置可以參考以下連結
> https://hi-founder.com/p/gcp-gcloud-config-%E8%A8%AD%E5%AE%9A%E9%85%8D%E7%BD%AE%E4%BD%BF%E7%94%A8/**

## 

**參考資料**

* 初始化 gcloud CLI 
  * https://cloud.google.com/sdk/docs/initializing?authuser=1&hl=zh-cn
  
  * https://kejyuntw.gitbooks.io/google-cloud-platform-learning-notes/content/gcloud/gcloud-README.html

* gcloud config 配置指令
  https://hi-founder.com/p/gcp-gcloud-config-%E8%A8%AD%E5%AE%9A%E9%85%8D%E7%BD%AE%E4%BD%BF%E7%94%A8/

* gsutil 下載指令
  https://pjchender.dev/cloud-service/gcp-cloud-storage/

<!--不確定這個筆記是不是全部正確的-->