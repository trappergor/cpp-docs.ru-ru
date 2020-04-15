---
title: Интернет URL Разбор глобалов и помощников
ms.date: 04/03/2017
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
ms.openlocfilehash: 742b381ecb55c433d0f384174b7612fcc21e9716
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356608"
---
# <a name="internet-url-parsing-globals-and-helpers"></a>Интернет URL Разбор глобалов и помощников

Когда клиент отправляет запрос на интернет-сервер, можно использовать один из глобальных URL-адресов для извлечения информации о клиенте. Функции помощника обеспечивают другие возможности Интернета.

## <a name="internet-url-parsing-globals"></a>Глобальные объекты разбора URL-адресов

|||
|-|-|
|[AfxParseURL](#afxparseurl)|Сравнивает строку URL и возвращает тип службы и ее компоненты.|
|[AfxParseURLEx](#afxparseurlex)|Сравнивает строку URL и возвращает тип службы и ее компоненты, а также предоставляет имя пользователя и пароль.|

## <a name="other-internet-helpers"></a>Другие интернет-помощники

|||
|-|-|
|[AfxThrowInternetException](#afxthrowinternetexception)|Бросает исключение, связанное с подключением к Интернету.|
|[AfxGetInternetHandleType](#afxgetinternethandletype)|Определяет тип ручки Интернета.|

## <a name="afxparseurl"></a><a name="afxparseurl"></a>AfxParseURL

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

*pstrURL*<br/>
Указатель на строку, содержащую URL для разбора.

*dwServiceType*<br/>
Указывает тип Интернет-сервиса. Возможны следующие значения:

- AFX_INET_SERVICE_FTP

- AFX_INET_SERVICE_HTTP

- AFX_INET_SERVICE_HTTPS

- AFX_INET_SERVICE_GOPHER

- AFX_INET_SERVICE_FILE

- AFX_INET_SERVICE_MAILTO

- AFX_INET_SERVICE_NEWS

- AFX_INET_SERVICE_NNTP

- AFX_INET_SERVICE_TELNET

- AFX_INET_SERVICE_WAIS

- AFX_INET_SERVICE_MID

- AFX_INET_SERVICE_CID

- AFX_INET_SERVICE_PROSPERO

- AFX_INET_SERVICE_AFS

- AFX_INET_SERVICE_UNK

*strServer*<br/>
Первый сегмент URL-адреса после типа службы.

*strObject*<br/>
Объект, на который ссылается URL(может быть пустым).

*nПорт*<br/>
Определяется либо с сервера или объекта части URL, если либо существует.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если URL был успешно разогнан; в противном случае 0, если он пуст или не содержит известный тип Интернет-услуг.

### <a name="remarks"></a>Remarks

Он разбирает строку URL и возвращает тип службы и ее компоненты.

Например, `AfxParseURL` разбирать URL-адреса формы *service://server/dir/dir/object.ext:port* и возвращает ее компоненты, хранящиеся следующим образом:

*strServer* "сервер"

*strObject* "/dir/dir/object/object.ext"

*nПорт* #port

*dwServiceType* #service

> [!NOTE]
> Чтобы вызвать эту функцию, проект должен включать В себя AFXINET. H.

### <a name="requirements"></a>Требования

  **Заголовок** afxinet.h

## <a name="afxparseurlex"></a><a name="afxparseurlex"></a>AfxParseURLEx

Эта глобальная функция является расширенной версией [AfxParseURL](#afxparseurl) и используется в [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

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

*pstrURL*<br/>
Указатель на строку, содержащую URL для разбора.

*dwServiceType*<br/>
Указывает тип Интернет-сервиса. Возможны следующие значения:

- AFX_INET_SERVICE_FTP

- AFX_INET_SERVICE_HTTP

- AFX_INET_SERVICE_HTTPS

- AFX_INET_SERVICE_GOPHER

- AFX_INET_SERVICE_FILE

- AFX_INET_SERVICE_MAILTO

- AFX_INET_SERVICE_NEWS

- AFX_INET_SERVICE_NNTP

- AFX_INET_SERVICE_TELNET

- AFX_INET_SERVICE_WAIS

- AFX_INET_SERVICE_MID

- AFX_INET_SERVICE_CID

- AFX_INET_SERVICE_PROSPERO

- AFX_INET_SERVICE_AFS

- AFX_INET_SERVICE_UNK

*strServer*<br/>
Первый сегмент URL-адреса после типа службы.

*strObject*<br/>
Объект, на который ссылается URL(может быть пустым).

*nПорт*<br/>
Определяется либо с сервера или объекта части URL, если либо существует.

*strUsername*<br/>
Ссылка на `CString` объект, содержащий имя пользователя.

*strPassword*<br/>
Ссылка на `CString` объект, содержащий пароль пользователя.

*dwFlags*<br/>
Флаги, контролирующие, как разбирать URL. Может быть сочетание следующих значений:

|Значение|Значение|
|-----------|-------------|
|ICU_DECODE|Преобразование последовательностей побега %XX в символы.|
|ICU_NO_ENCODE|Не конвертировать небезопасные символы, чтобы избежать последовательности.|
|ICU_NO_META|Не удаляйте мета-последовательности (например, «Я». и "..") с URL-адреса.|
|ICU_ENCODE_SPACES_ONLY|Кодировать только пробелы.|
|ICU_BROWSER_MODE|Не кодировать и не расшифровывать символы после ''' или '', и не удаляйте заднее белое пространство после ''. Если это значение не указано, весь URL закодирован и задняющее белое пространство удаляется.|

Если вы используете MFC по умолчанию, который не флаги, функция преобразует все \\небезопасные символы \\и мета последовательности (например, .,', и ...), чтобы избежать последовательностей.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если URL был успешно разогнан; в противном случае 0, если он пуст или не содержит известный тип Интернет-услуг.

### <a name="remarks"></a>Remarks

Он разбирает строку URL и возвращает тип службы и ее компоненты, а также предоставляет имя пользователя и пароль. Флаги показывают, как обрабатываются небезопасные символы.

> [!NOTE]
> Чтобы вызвать эту функцию, проект должен включать В себя AFXINET. H.

### <a name="requirements"></a>Требования

  **Заголовок** afxinet.h

## <a name="afxgetinternethandletype"></a><a name="afxgetinternethandletype"></a>AfxGetInternetHandleType

Используйте эту глобальную функцию для определения типа ручек Интернета.

### <a name="syntax"></a>Синтаксис

  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );
```

### <a name="parameters"></a>Параметры

*х-жери*<br/>
Ручка для интернет-запроса.

### <a name="return-value"></a>Возвращаемое значение

Любой из типов Интернет-услуг, определенных WININET. H. Список этих интернет-сервисов можно ознакомиться в разделе «Замечания». Если ручка null или не распознана, функция возвращается AFX_INET_SERVICE_UNK.

### <a name="remarks"></a>Remarks

Следующий список включает в `AfxGetInternetHandleType`себя возможные типы Интернета, возвращенные .

- INTERNET_HANDLE_TYPE_INTERNET

- INTERNET_HANDLE_TYPE_CONNECT_FTP

- INTERNET_HANDLE_TYPE_CONNECT_GOPHER

- INTERNET_HANDLE_TYPE_CONNECT_HTTP

- INTERNET_HANDLE_TYPE_FTP_FIND

- INTERNET_HANDLE_TYPE_FTP_FIND_HTML

- INTERNET_HANDLE_TYPE_FTP_FILE

- INTERNET_HANDLE_TYPE_FTP_FILE_HTML

- INTERNET_HANDLE_TYPE_GOPHER_FIND

- INTERNET_HANDLE_TYPE_GOPHER_FIND_HTML

- INTERNET_HANDLE_TYPE_GOPHER_FILE

- INTERNET_HANDLE_TYPE_GOPHER_FILE_HTML

- INTERNET_HANDLE_TYPE_HTTP_REQUEST

> [!NOTE]
> Для вызова этой функции проект должен включать В себя AFXINET. H.

### <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

## <a name="afxthrowinternetexception"></a><a name="afxthrowinternetexception"></a>AfxThrowInternetИсключениек

Бросает исключение из Интернета.

### <a name="syntax"></a>Синтаксис

```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );
```

### <a name="parameters"></a>Параметры

*Dwcontext*<br/>
Идентификатор контекста для операции, вызвавшей ошибку. Значение *dwContext* по умолчанию первоначально указывается в [CInternetSession](cinternetsession-class.md) и передается классам [CInternetConnection](cinternetconnection-class.md)- и [CInternetFile](cinternetfile-class.md)- производным. Для конкретных операций, выполняемых на подключении или файле, вы обычно переопределяют значение по умолчанию с помощью собственного *dwContext.* Затем это значение возвращается [в CInternetSession::OnStatusCallback](cinternetsession-class.md#onstatuscallback) для определения статуса конкретной операции.

*dwОшибка*<br/>
Ошибка, ставшая причиной исключения.

### <a name="remarks"></a>Remarks

Вы несете ответственность за определение причины на основе кода ошибки операционной системы.

> [!NOTE]
> Чтобы вызвать эту функцию, проект должен включать В себя AFXINET. H.

### <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[Класс CInternetException](cinternetexception-class.md)<br/>
[AfxParseURL](internet-url-parsing-globals.md#afxparseurl)
