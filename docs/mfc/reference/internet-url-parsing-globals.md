---
title: "Глобальные объекты разбора URL Интернет | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.isapi
dev_langs:
- C++
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 3aec259acae2f5e9c9b65ac4e5c898ca57ff3d52
ms.lasthandoff: 02/24/2017

---
# <a name="internet-url-parsing-globals"></a>Глобальные объекты разбора URL-адресов
Когда клиент отправляет запрос к Интернет-серверу, можно использовать один из глобальные объекты разбора URL-адрес для получения сведений о клиенте.  
  
### <a name="internet-url-parsing-globals"></a>Глобальные объекты разбора URL-адресов  
  
|||  
|-|-|  
|[AfxParseURL](#afxparseurl)|Анализирует строку URL-адреса и возвращает тип службы и ее компонентов.|  
|[AfxParseURLEx](#afxparseurlex)|Анализирует строку URL-адреса и возвращает тип службы и ее компонентов, а также имя пользователя и пароль.|  
  
##  <a name="a-nameafxparseurla--afxparseurl"></a><a name="afxparseurl"></a>AfxParseURL  
 Этот глобальный используется в [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
```   
BOOL AFXAPI AfxParseURL(
    LPCTSTR pstrURL,  
    DWORD& dwServiceType,  
    CString& strServer,  
    CString& strObject,  
    INTERNET_PORT& nPort); 
```  
  
### <a name="parameters"></a>Параметры  
 *pstrURL*  
 Указатель на строку, содержащую URL-адрес для синтаксического анализа.  
  
 `dwServiceType`  
 Указывает тип службы Интернета. Ниже приведены возможные значения.  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 Первый сегмент URL-адрес после типа службы.  
  
 `strObject`  
 Объект, который называют URL-адрес (может быть пустым).  
  
 `nPort`  
 Определить из частей URL-адрес сервера или объекта, если они существуют.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если URL-адрес был проанализирован успешно; в противном случае — 0, если он пуст или не содержит известного типа службы IIS.  
  
### <a name="remarks"></a>Примечания  
 Он анализирует строку URL-адрес и возвращает тип службы и ее компонентов.  
  
 Например `AfxParseURL` анализирует URL-адреса формы **service://server/dir/dir/object.ext:port** и возвращает его компоненты, следующим образом:  
  
 `strServer`== «сервер»  
  
 `strObject`==» или dir/dir/object/object.ext»  
  
 `nPort`== #port  
  
 `dwServiceType`== #service  
  
> [!NOTE]
>  Вызов этой функции, проект должен содержать AFXINET. З.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxinet.h  
  
##  <a name="a-nameafxparseurlexa--afxparseurlex"></a><a name="afxparseurlex"></a>AfxParseURLEx  
 Это глобальная функция является расширенной версией [AfxParseURL](#afxparseurl) и используется в [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
```   
BOOL AFXAPI AfxParseURLEx(
    LPCTSTR pstrURL,  
    DWORD& dwServiceType,  
    CString& strServer,  
    CString& strObject,  
    INTERNET_PORT& nPort,  
    CString& strUsername,  
    CString& strPassword,  
    DWORD dwFlags = 0); 
```  
  
### <a name="parameters"></a>Параметры  
 *pstrURL*  
 Указатель на строку, содержащую URL-адрес для синтаксического анализа.  
  
 `dwServiceType`  
 Указывает тип службы Интернета. Ниже приведены возможные значения.  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 Первый сегмент URL-адрес после типа службы.  
  
 `strObject`  
 Объект, который называют URL-адрес (может быть пустым).  
  
 `nPort`  
 Определить из частей URL-адрес сервера или объекта, если они существуют.  
  
 *названием strUsername*  
 Ссылку на `CString` объект, содержащий имя пользователя.  
  
 `strPassword`  
 Ссылку на `CString` объект, содержащий пароль пользователя.  
  
 `dwFlags`  
 Флаги управления как выполнить синтаксический анализ URL-адрес. Может быть сочетанием следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|**ICU_DECODE**|Преобразуйте % XX escape-последовательности символов.|  
|**ICU_NO_ENCODE**|Не следует преобразовывать небезопасных символов в escape-последовательность.|  
|**ICU_NO_META**|Не удаляйте meta последовательности (например, «\». и «\»...) URL-адреса.|  
|**ICU_ENCODE_SPACES_ONLY**|Кодирование только пробелы.|  
|**ICU_BROWSER_MODE**|Не кодировать и декодировать символы после «#» или "и не удаляет пробелы после ''. Если это значение не задано, кодируется весь URL-адрес и конечные пробелы удаляются.|  
  
 При использовании по умолчанию MFC, который является никакие флаги, функция преобразует все небезопасные символы и последовательностей meta (такие как \\., \.., и \\...) в escape-последовательности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если URL-адрес был проанализирован успешно; в противном случае — 0, если он пуст или не содержит известного типа службы IIS.  
  
### <a name="remarks"></a>Примечания  
 Он анализирует строку URL-адреса и возвращает тип службы и ее компонентов, а также пароля и имени пользователя. Флаги указывают, как небезопасные символы обрабатываются.  
  
> [!NOTE]
>  Вызов этой функции, проект должен содержать AFXINET. З.  

### <a name="requirements"></a>Требования  
  **Заголовок** afxinet.h  
    
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

