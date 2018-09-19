---
title: Класс cUrl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CUrl
- ATLUTIL/ATL::CUrl
- ATLUTIL/ATL::CUrl::CUrl
- ATLUTIL/ATL::CUrl::Canonicalize
- ATLUTIL/ATL::CUrl::Clear
- ATLUTIL/ATL::CUrl::CrackUrl
- ATLUTIL/ATL::CUrl::CreateUrl
- ATLUTIL/ATL::CUrl::GetExtraInfo
- ATLUTIL/ATL::CUrl::GetExtraInfoLength
- ATLUTIL/ATL::CUrl::GetHostName
- ATLUTIL/ATL::CUrl::GetHostNameLength
- ATLUTIL/ATL::CUrl::GetPassword
- ATLUTIL/ATL::CUrl::GetPasswordLength
- ATLUTIL/ATL::CUrl::GetPortNumber
- ATLUTIL/ATL::CUrl::GetScheme
- ATLUTIL/ATL::CUrl::GetSchemeName
- ATLUTIL/ATL::CUrl::GetSchemeNameLength
- ATLUTIL/ATL::CUrl::GetUrlLength
- ATLUTIL/ATL::CUrl::GetUrlPath
- ATLUTIL/ATL::CUrl::GetUrlPathLength
- ATLUTIL/ATL::CUrl::GetUserName
- ATLUTIL/ATL::CUrl::GetUserNameLength
- ATLUTIL/ATL::CUrl::SetExtraInfo
- ATLUTIL/ATL::CUrl::SetHostName
- ATLUTIL/ATL::CUrl::SetPassword
- ATLUTIL/ATL::CUrl::SetPortNumber
- ATLUTIL/ATL::CUrl::SetScheme
- ATLUTIL/ATL::CUrl::SetSchemeName
- ATLUTIL/ATL::CUrl::SetUrlPath
- ATLUTIL/ATL::CUrl::SetUserName
dev_langs:
- C++
helpviewer_keywords:
- CUrl class
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0ab7906961936239ac564137d0760e6d64de9de
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068225"
---
# <a name="curl-class"></a>Класс cUrl

Этот класс представляет URL-адрес. Он позволяет управлять каждый элемент URL-адреса независимо от других ли синтаксический анализ URL-адрес существующей строки или создании строки с нуля.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class CUrl
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CUrl::CUrl](#curl)|Конструктор.|
|[CUrl:: ~ CUrl](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CUrl::Canonicalize](#canonicalize)|Этот метод используется для преобразования строки URL-адрес в канонической форме.|
|[CUrl::Clear](#clear)|Вызовите этот метод, чтобы очистить все поля URL-адрес.|
|[CUrl::CrackUrl](#crackurl)|Вызовите этот метод, чтобы декодировать и анализировать URL-адрес.|
|[CUrl::CreateUrl](#createurl)|Этот метод используется для создания URL-адрес.|
|[CUrl::GetExtraInfo](#getextrainfo)|Вызовите этот метод, чтобы получить дополнительные данные (такие как *текст* или # *текст*) из URL-адрес.|
|[CUrl::GetExtraInfoLength](#getextrainfolength)|Вызовите этот метод, чтобы получить нужные дополнительные данные (такие как *текст* или # *текст*) для получения URL-адреса.|
|[CUrl::GetHostName](#gethostname)|Этот метод используется для получения имени узла в URL-адресе.|
|[CUrl::GetHostNameLength](#gethostnamelength)|Вызовите этот метод, чтобы получить длину имени узла.|
|[CUrl::GetPassword](#getpassword)|Вызовите этот метод, чтобы получить пароль в URL-адресе.|
|[CUrl::GetPasswordLength](#getpasswordlength)|Вызовите этот метод, чтобы получить длину пароля.|
|[CUrl::GetPortNumber](#getportnumber)|Вызовите этот метод, чтобы получить имя порта, с точки зрения ATL_URL_PORT.|
|[CUrl::GetScheme](#getscheme)|Вызовите этот метод, чтобы получить схему URL-адрес.|
|[CUrl::GetSchemeName](#getschemename)|Вызовите этот метод, чтобы получить имя схемы URL-адрес.|
|[CUrl::GetSchemeNameLength](#getschemenamelength)|Вызовите этот метод, чтобы получить имя схемы URL-адрес.|
|[CUrl::GetUrlLength](#geturllength)|Вызовите этот метод, чтобы получить URL-адрес.|
|[CUrl::GetUrlPath](#geturlpath)|Этот метод используется для получения пути URL-адрес.|
|[CUrl::GetUrlPathLength](#geturlpathlength)|Этот метод используется для получения длины пути URL-адрес.|
|[CUrl::GetUserName](#getusername)|Этот метод используется для получения имени пользователя из URL-адрес.|
|[CUrl::GetUserNameLength](#getusernamelength)|Вызовите этот метод, чтобы получить длину имени пользователя.|
|[CUrl::SetExtraInfo](#setextrainfo)|Вызовите этот метод, чтобы задать нужные дополнительные данные (такие как *текст* или # *текст*) URL-адреса.|
|[CUrl::SetHostName](#sethostname)|Этот метод используется для задания имени узла.|
|[CUrl::SetPassword](#setpassword)|Этот метод используется для установки пароля.|
|[CUrl::SetPortNumber](#setportnumber)|Вызовите этот метод, чтобы задать номер порта с точки зрения ATL_URL_PORT.|
|[CUrl::SetScheme](#setscheme)|Вызовите этот метод, чтобы задать схему URL-адрес.|
|[CUrl::SetSchemeName](#setschemename)|Вызовите этот метод, чтобы задать имя схемы URL-адрес.|
|[CUrl::SetUrlPath](#seturlpath)|Этот метод используется для задания URL-пути.|
|[CUrl::SetUserName](#setusername)|Вызовите этот метод для задания имени пользователя.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CUrl::operator =](#operator_eq)|Назначает указанное `CUrl` объект с текущим `CUrl` объекта.|

## <a name="remarks"></a>Примечания

`CUrl` позволяет управлять поля URL-адреса, такие как путь или номер порта. `CUrl` принимает URL-адреса следующего вида:

\<Схема > ://\<имя пользователя >:\<пароль >\@\<имя узла >:\<номер_порта > /\<UrlPath >\<ExtraInfo >

(Некоторые поля являются обязательными). Например рассмотрим этот URL-адрес:

`http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents`

[CUrl::CrackUrl](#crackurl) разбирает его следующим образом:

- Схема: «http» или [ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)

- Имя пользователя: «someone»

- Пароль: «секрет»

- Имя узла: "`www.microsoft.com`"

- PortNumber: 80

- UrlPath: «visualc/stuff.htm»

- ExtraInfo: «#contents»

Чтобы управлять UrlPath поле (например), используйте [GetUrlPath](#geturlpath), [GetUrlPathLength](#geturlpathlength), и [SetUrlPath](#seturlpath). Используется [CreateUrl](#createurl) для создания полной строки URL-адрес.

## <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil.h

##  <a name="canonicalize"></a>  CUrl::Canonicalize

Этот метод используется для преобразования строки URL-адрес в канонической форме.

```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Флаги, определяющие канонизации. Если флаги не указаны (*dwFlags* = 0), метод преобразует все небезопасные символы и последовательности meta (такие как \\., \.., и \\...) для escape-последовательности. *dwFlags* может принимать одно из следующих значений:

- ATL_URL_BROWSER_MODE: Не кодирование или декодирование символов после «#» или «» и не удаляет пробелы после «». Если это значение не указано, кодируется весь URL-адрес и конечный пробел удаляется.

- ATL_URL _DECODE: преобразует все % XX последовательности символов, включая escape-последовательности, прежде чем анализируется URL-адрес.

- ATL_URL _ENCODE_PERCENT: кодирует все символы процента обнаружил. По умолчанию символы процента не кодируются.

- ATL_URL _ENCODE_SPACES_ONLY: кодирует только пробелы.

- ATL_URL _NO_ENCODE: не выполняет преобразование небезопасных символов в escape-последовательности.

- ATL_URL _NO_META: не приводит к удалению meta последовательности (такие как «. «и»..») из URL-адрес.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Преобразование в канонической форме включает преобразование небезопасных символов и пробелов в escape-последовательности.

##  <a name="clear"></a>  CUrl::Clear

Вызовите этот метод, чтобы очистить все поля URL-адрес.

```
inline void Clear() throw();
```

##  <a name="crackurl"></a>  CUrl::CrackUrl

Вызовите этот метод, чтобы декодировать и анализировать URL-адрес.

```
BOOL CrackUrl(LPCTSTR lpszUrl, DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Параметры

*lpszUrl*<br/>
URL-адрес.

*dwFlags*<br/>
Укажите ATL_URL_DECODE или ATL_URL_ESCAPE, чтобы преобразовать все escape-символов в *lpszUrl* реальные значения после синтаксического анализа. (Ранее Visual C++ 2005 ATL_URL_DECODE преобразовать все escape-символы перед анализом.)

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="createurl"></a>  CUrl::CreateUrl

Этот метод создает строку URL-адрес из поля компонентов объект CUrl.

```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```

### <a name="parameters"></a>Параметры

*lpszUrl*<br/>
Строковый буфер для хранения полной строки URL-адрес.

*pdwMaxLength*<br/>
Максимальная длина *lpszUrl* строковый буфер.

*dwFlags*<br/>
Укажите ATL_URL_ESCAPE для преобразования все escape-символов в *lpszUrl* реальные значения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Этот метод добавляет его отдельные поля для создания полной строки URL-адрес, используя следующий формат:

**\<Схема > ://\<пользователя >:\<передать >\@\<домена >:\<порт >\<путь >\<дополнительный >**

При вызове этого метода *pdwMaxLength* параметр изначально должен содержать максимальную длину буфера строки ссылается *lpszUrl* параметра. Значение *pdwMaxLength* параметр будет дополняться фактическую длину строки URL-адреса.

### <a name="example"></a>Пример

В этом примере демонстрируется создание объекта CUrl и извлечения его строки URL-адрес

[!code-cpp[NVC_ATL_Utilities#133](../../atl/codesnippet/cpp/curl-class_1.cpp)]

##  <a name="curl"></a>  CUrl::CUrl

Конструктор.

```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```

### <a name="parameters"></a>Параметры

*URL-адрес*<br/>
`CUrl` Объект для копирования для создания URL-адрес.

##  <a name="dtor"></a>  CUrl:: ~ CUrl

Деструктор

```
~CUrl() throw();
```

##  <a name="getextrainfo"></a>  CUrl::GetExtraInfo

Вызовите этот метод, чтобы получить дополнительные данные (такие как *текст* или # *текст*) из URL-адрес.

```
inline LPCTSTR GetExtraInfo() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает строку, содержащую нужные дополнительные данные.

##  <a name="getextrainfolength"></a>  CUrl::GetExtraInfoLength

Вызовите этот метод, чтобы получить нужные дополнительные данные (такие как *текст* или # *текст*) для получения URL-адреса.

```
inline DWORD GetExtraInfoLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину строки, содержащей дополнительную информацию.

##  <a name="gethostname"></a>  CUrl::GetHostName

Этот метод используется для получения имени узла в URL-адресе.

```
inline LPCTSTR GetHostName() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает имя узла.

##  <a name="gethostnamelength"></a>  CUrl::GetHostNameLength

Вызовите этот метод, чтобы получить длину имени узла.

```
inline DWORD GetHostNameLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину имени узла.

##  <a name="getpassword"></a>  CUrl::GetPassword

Вызовите этот метод, чтобы получить пароль в URL-адресе.

```
inline LPCTSTR GetPassword() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает пароль.

##  <a name="getpasswordlength"></a>  CUrl::GetPasswordLength

Вызовите этот метод, чтобы получить длину пароля.

```
inline DWORD GetPasswordLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину пароля.

##  <a name="getportnumber"></a>  CUrl::GetPortNumber

Вызовите этот метод, чтобы получить имя порта.

```
inline ATL_URL_PORT GetPortNumber() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает номер порта.

##  <a name="getscheme"></a>  CUrl::GetScheme

Вызовите этот метод, чтобы получить схему URL-адрес.

```
inline ATL_URL_SCHEME GetScheme() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает [ATL_URL_SCHEME](atl-url-scheme-enum.md) значение, описывающее схему URL-адреса.

##  <a name="getschemename"></a>  CUrl::GetSchemeName

Вызовите этот метод, чтобы получить имя схемы URL-адрес.

```
inline LPCTSTR GetSchemeName() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает имя схемы URL-адрес (например, «http» или «ftp»).

##  <a name="getschemenamelength"></a>  CUrl::GetSchemeNameLength

Вызовите этот метод, чтобы получить имя схемы URL-адрес.

```
inline DWORD GetSchemeNameLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину имени схемы URL-адрес.

##  <a name="geturllength"></a>  CUrl::GetUrlLength

Вызовите этот метод, чтобы получить URL-адрес.

```
inline DWORD GetUrlLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину URL-адрес.

##  <a name="geturlpath"></a>  CUrl::GetUrlPath

Этот метод используется для получения пути URL-адрес.

```
inline LPCTSTR GetUrlPath() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает путь URL-адрес.

##  <a name="geturlpathlength"></a>  CUrl::GetUrlPathLength

Этот метод используется для получения длины пути URL-адрес.

```
inline DWORD GetUrlPathLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину пути URL-адрес.

##  <a name="getusername"></a>  CUrl::GetUserName

Этот метод используется для получения имени пользователя из URL-адрес.

```
inline LPCTSTR GetUserName() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает имя пользователя.

##  <a name="getusernamelength"></a>  CUrl::GetUserNameLength

Вызовите этот метод, чтобы получить длину имени пользователя.

```
inline DWORD GetUserNameLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину имени пользователя.

##  <a name="operator_eq"></a>  CUrl::operator =

Назначает указанное `CUrl` объект с текущим `CUrl` объекта.

```
CUrl& operator= (const CUrl& urlThat) throw();
```

### <a name="parameters"></a>Параметры

*URL-адрес*<br/>
`CUrl` Объект для копирования в текущий объект.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на текущий объект.

##  <a name="setextrainfo"></a>  CUrl::SetExtraInfo

Вызовите этот метод, чтобы задать нужные дополнительные данные (такие как *текст* или # *текст*) URL-адреса.

```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```

### <a name="parameters"></a>Параметры

*lpszInfo*<br/>
Строка, содержащая дополнительные сведения для включения в URL-адрес.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="sethostname"></a>  CUrl::SetHostName

Этот метод используется для задания имени узла.

```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```

### <a name="parameters"></a>Параметры

*lpszHost*<br/>
Имя узла.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="setpassword"></a>  CUrl::SetPassword

Этот метод используется для установки пароля.

```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```

### <a name="parameters"></a>Параметры

*lpszPass*<br/>
Пароль.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="setportnumber"></a>  CUrl::SetPortNumber

Вызовите этот метод, чтобы задать номер порта.

```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```

### <a name="parameters"></a>Параметры

*nPrt*<br/>
Номер порта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="setscheme"></a>  CUrl::SetScheme

Вызовите этот метод, чтобы задать схему URL-адрес.

```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```

### <a name="parameters"></a>Параметры

*nScheme*<br/>
Один из [ATL_URL_SCHEME](atl-url-scheme-enum.md) значения для схемы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Можно также задать схему по имени (см. в разделе [CUrl::SetSchemeName](#setschemename)).

##  <a name="setschemename"></a>  CUrl::SetSchemeName

Вызовите этот метод, чтобы задать имя схемы URL-адрес.

```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```

### <a name="parameters"></a>Параметры

*lpszSchm*<br/>
Имя схемы, URL-адрес.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

Можно также задать схему с помощью [ATL_URL_SCHEME](atl-url-scheme-enum.md) констант (см. в разделе [CUrl::SetScheme](#setscheme)).

##  <a name="seturlpath"></a>  CUrl::SetUrlPath

Этот метод используется для задания URL-пути.

```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```

### <a name="parameters"></a>Параметры

*lpszPath*<br/>
URL-адрес.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

##  <a name="setusername"></a>  CUrl::SetUserName

Вызовите этот метод для задания имени пользователя.

```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```

### <a name="parameters"></a>Параметры

*lpszUser*<br/>
Имя пользователя.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения FALSE в случае сбоя.

## <a name="see-also"></a>См. также

[Классы](../../atl/reference/atl-classes.md)
