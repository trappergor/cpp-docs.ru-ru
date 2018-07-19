---
title: Глобальные объекты разбора URL-адреса Интернета и вспомогательные методы | Документация Майкрософт
ms.custom: ''
ms.date: 04/03/2017
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.isapi
dev_langs:
- C++
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 839e07db88edf8b1bb007a6aedfe90c94732c784
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335735"
---
# <a name="internet-url-parsing-globals-and-helpers"></a>Глобальные объекты разбора URL-адреса Интернета и вспомогательные методы
Когда клиент отправляет запрос на сервер Интернета, можно использовать один из глобальные объекты разбора URL-адрес для получения сведений о клиенте. Вспомогательные функции предоставляют другие функциональные возможности Интернета.
  
## <a name="internet-url-parsing-globals"></a>Глобальные объекты разбора URL-адресов  
  
|||  
|-|-|  
|[AfxParseURL](#afxparseurl)|Анализирует строку URL-адреса и возвращает тип службы и его компонентов.|  
|[AfxParseURLEx](#afxparseurlex)|Анализирует строку URL-адреса и возвращает тип службы и ее компонентов, а также указав имя пользователя и пароль.|  

## <a name="other-internet-helpers"></a>Другие вспомогательные пакеты Internet
|||
|-|-|
|[AfxThrowInternetException](#afxthrowinternetexception)|Создает исключение, связанные с подключением к Интернету.|
|[AfxGetInternetHandleType](#afxgetinternethandletype)|Определяет тип дескриптора Интернета.|
  
##  <a name="afxparseurl"></a>  AfxParseURL  
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
 Указатель на строку, содержащую URL-адрес, который необходимо проанализировать.  
  
 *dwServiceType*  
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
  
 *strServer*  
 Первый сегмент URL-адреса после типа службы.  
  
 *strObject*  
 Объект, который ссылается URL-адрес (может быть пустым).  
  
 *nPort*  
 Определяются на основе сервера или объект части URL-адрес, если они существуют.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если URL-адрес был успешно проанализировано; в противном случае — 0, если он пуст или не содержит известного типа службы Интернета.  
  
### <a name="remarks"></a>Примечания  
 Он анализирует строку URL-адреса и возвращает тип службы и ее компонентов.  
  
 Например `AfxParseURL` выполняет синтаксический анализ URL-адреса формы *service://server/dir/dir/object.ext:port* и возвращает его компоненты, которые хранятся следующим образом:  
  
 *strServer* == «server»  
  
 *strObject* == «/ dir/dir/object/object.ext»  
  
 *nPort* == #port  
  
 *dwServiceType* == #service  
  
> [!NOTE]
>  Чтобы вызвать эту функцию, ваш проект должен включать AFXINET. З.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxinet.h  
  
##  <a name="afxparseurlex"></a>  AfxParseURLEx  
 Это является расширенной версией набора [AfxParseURL](#afxparseurl) и используется в [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
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
 Указатель на строку, содержащую URL-адрес, который необходимо проанализировать.  
  
 *dwServiceType*  
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
  
 *strServer*  
 Первый сегмент URL-адреса после типа службы.  
  
 *strObject*  
 Объект, который ссылается URL-адрес (может быть пустым).  
  
 *nPort*  
 Определяются на основе сервера или объект части URL-адрес, если они существуют.  
  
 *strUsername*  
 Ссылку на `CString` объект, содержащий имя пользователя.  
  
 *strPassword*  
 Ссылку на `CString` объект, содержащий пароль пользователя.  
  
 *dwFlags*  
 Флаги, управляющие как производить синтаксический анализ URL-адрес. Может быть сочетанием следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|ICU_DECODE|Преобразуйте % XX escape-последовательности символов.|  
|ICU_NO_ENCODE|Не следует преобразовывать небезопасных символов в escape-последовательности.|  
|ICU_NO_META|Не удаляйте meta последовательности (например, «\.» и «\»..) в URL-адресе.|  
|ICU_ENCODE_SPACES_ONLY|Кодирование только пробелы.|  
|ICU_BROWSER_MODE|Не кодирование или декодирование символов после символа «#» или "и не удаляйте пробелы после ''. Если это значение не указано, кодируется весь URL-адрес и конечный пробел удаляется.|  
  
 Если вы используете стандартные MFC, которая является никакие флаги, функция преобразует удаленными небезопасными символами и последовательностями meta (такие как \\., \.., и \\...) для escape-последовательности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если URL-адрес был успешно проанализировано; в противном случае — 0, если он пуст или не содержит известного типа службы Интернета.  
  
### <a name="remarks"></a>Примечания  
 Он анализирует строку URL-адреса и возвращает тип службы и ее компонентов, а также указав имя пользователя и пароль. Флаги указывают, как небезопасные символы обрабатываются.  
  
> [!NOTE]
>  Чтобы вызвать эту функцию, ваш проект должен включать AFXINET. З.  

### <a name="requirements"></a>Требования  
  **Заголовок** afxinet.h  
    
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
 
## <a name="afxgetinternethandletype"></a>  AfxGetInternetHandleType
Используйте эту глобальную функцию для определения типа дескриптора Интернета.  
   
### <a name="syntax"></a>Синтаксис  
  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );  
```
### <a name="parameters"></a>Параметры  
 *hQuery*  
 Дескриптор запроса на Интернет.  
   
### <a name="return-value"></a>Возвращаемое значение  
 Любой из типов служб Интернета, определяется WININET. З. См. в разделе "Примечания" список этих служб Интернета. Если дескриптор имеет значение NULL или не распознан, функция возвращает AFX_INET_SERVICE_UNK.  
   
### <a name="remarks"></a>Примечания  
 В следующем списке перечислены возможные типы Internet, возвращенный `AfxGetInternetHandleType`.  
  
-   INTERNET_HANDLE_TYPE_INTERNET  
  
-   INTERNET_HANDLE_TYPE_CONNECT_FTP  
  
-   INTERNET_HANDLE_TYPE_CONNECT_GOPHER  
  
-   INTERNET_HANDLE_TYPE_CONNECT_HTTP  
  
-   INTERNET_HANDLE_TYPE_FTP_FIND  
  
-   INTERNET_HANDLE_TYPE_FTP_FIND_HTML  
  
-   INTERNET_HANDLE_TYPE_FTP_FILE  
  
-   INTERNET_HANDLE_TYPE_FTP_FILE_HTML  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FIND  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FIND_HTML  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FILE  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FILE_HTML  
  
-   INTERNET_HANDLE_TYPE_HTTP_REQUEST  
  
> [!NOTE]
>  Чтобы вызвать эту функцию, ваш проект должен включать AFXINET. З.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [AfxParseURL](internet-url-parsing-globals.md#afxparseurl)
 
## <a name="afxthrowinternetexception"></a>  AfxThrowInternetException
Создает исключение, Интернет.  
   
### <a name="syntax"></a>Синтаксис    
```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );  
```
### <a name="parameters"></a>Параметры  
 *dwContext*  
 Идентификатор контекста для операции, которая вызвала ошибку. Значение по умолчанию *dwContext* изначально указывается в [CInternetSession](cinternetsession-class.md) и передается [CInternetConnection](cinternetconnection-class.md)- и [CInternetFile](cinternetfile-class.md)-производные классы. Для определенных операций, выполняемых на подключение или файл, обычно переопределить значение по умолчанию с *dwContext* своим собственным. Это значение затем возвращается к [CInternetSession::OnStatusCallback](cinternetsession-class.md#onstatuscallback) для идентификации состояние конкретной операции. 
  
 *dwError*  
 Ошибки, вызвавшей исключение.  
   
### <a name="remarks"></a>Примечания  
 Вы несете ответственность за определение причины, по коду ошибки операционной системы.  
  
> [!NOTE]
>  Чтобы вызвать эту функцию, ваш проект должен включать AFXINET. З.  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
 [Класс CInternetException](cinternetexception-class.md)   
 [THROW](#throw)
 

