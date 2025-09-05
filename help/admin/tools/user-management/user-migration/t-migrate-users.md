---
description: 將使用者從舊版 Analytics 使用者管理系統移轉至 Admin Console。
title: 移轉 Adobe ID 的 Analytics 使用者帳戶
feature: Admin Tools
exl-id: 198367a1-8156-4cc3-af8a-d92c61699eda
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 99%

---

# 移轉 Adobe ID 的 Analytics 使用者帳戶

將使用者從舊版 Analytics 使用者管理系統移轉至 Admin Console。

>[!NOTE]
>
>如果未透過 Experience Cloud 登入的管理員嘗試存取「使用者 ID 移轉」工具，系統會將他們重新導向至 Experience Cloud 登入頁面。

1. 導覽至&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 使用者 ID 移轉」]**。

   ![](/help/admin/tools/user-management/user-migration/assets/migration-progress.png)

   「使用者 ID 移轉」頁面有&#x200B;*「移轉程序」*&#x200B;和&#x200B;*「使用者資訊」*&#x200B;等兩個區段。

## 「移轉程序」

<table id="table_F9F1CFF762C745E198CB075A02BA2DDA"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 階段 </th> 
      <th colname="col2" class="entry"> 說明 </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>完成移轉程序 </p> </td> 
      <td colname="col2"> <p>使用者已接受邀請。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>停用舊版登入 </p> </td> 
      <td colname="col2"> <p>使用公司 ID 的舊版登入已停用。使用者現可使用 Adobe ID 或 Enterprise ID 存取 Experience Cloud。所有使用者均已達到這個階段後，移轉程序便告完成。 </p> <p>舊版登入會在移轉過程中遭到停用。系統會將使用者重新導向至 <span class="filepath">experiencecloud.adobe.com</span>，且必須使用 Adobe ID 或 Enterprise ID 登入。 </p> </td> 
   </tr> 
   </tbody> 
   </table>

## 使用者資訊

「使用者資訊」摘述貴組織的使用者 (以網域名稱區隔)。

<table id="table_3822E27AF81E4A188562FEB5131548A5"> 
<thead> 
<tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
</tr>
</thead>
<tbody> 
<tr> 
   <td colname="col1"> <p>網域 </p> </td> 
   <td colname="col2"> <p>網域必須是目前 Analytics 使用者群的電子郵件 ID 所專屬。網域只能由單一組織申請，而且只有系統管理員可以申請網域。如需詳細資訊，請參閱<a href="https://helpx.adobe.com/tw/enterprise/help/request-access-to-claimed-domain.html">要求已申請之網域的存取權</a>。 </p> </td> 
</tr> 
<tr> 
   <td colname="col1"> <p>申請的網域 </p> </td> 
   <td colname="col2"> <p>若要以 Enterprise 或 Federated ID 移轉使用者，您必須是「系統管理員」，並在移轉使用者前透過 Adobe Admin Console 申請可用網域。 如需更多詳情，請參閱<a href="https://helpx.adobe.com/tw/enterprise/help/identity.html">此處</a>。 </p> <p>如果您不想申請 Enterprise 或 Federated ID 的網域，請跳過此步驟，並以 Adobe ID 移轉使用者。如需有關 ID 類型的詳細資訊，請參閱<a href="https://helpx.adobe.com/tw/enterprise/help/identity.html">此處</a>。 </p> </td> 
</tr> 
</tbody> 
</table>

1. 找到包含您要移轉之使用者 ID 的網域，然後按一下&#x200B;**[!UICONTROL 「需要移轉」]**&#x200B;底下的&#x200B;**[!UICONTROL 「選取使用者」]**。
1. 在 [!DNL Users] 頁面中，選取您要移轉的使用者，然後按一下&#x200B;**[!UICONTROL 「移轉」]**。

   按一下&#x200B;**[!UICONTROL 「移轉」]**&#x200B;後，使用者會收到邀請 (「啟動移轉程序」)，而且必須接受。此動作會將使用者 ID 移動到「完成移轉程序」。接著，您就可以關閉 `[!DNL my.omniture.com].` 的舊版存取權

   ![](/help/admin/tools/user-management/user-migration/assets/user-info.png)

1. 指定您要移轉使用者的 ID 類型 (Adobe ID 或 Enterprise ID)

   移轉使用者後，「移轉狀態」欄下方的狀態會從 *`Not Initiated`* 變更為 *`Migrated`*。

   如果顯示 *`Failed`*，將游標停留在圖示上方就會顯示移轉失敗的原因。
