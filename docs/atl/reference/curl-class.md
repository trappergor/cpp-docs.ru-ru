---
title: "Класс cUrl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
helpviewer_keywords: CUrl class
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7e05cb6ca1aa9ffd9a827fd9f907fdc39d5bde13
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="curl-class"></a>Класс cUrl
Этот класс представляет URL-адрес. Он позволяет управлять каждый элемент URL-адреса независимо от других ли синтаксический анализ URL-адрес существующей строки или создании строки с нуля.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CUrl
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CUrl::CUrl](#curl)|Конструктор.|  
|[CUrl:: ~ CUrl](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CUrl::Canonicalize](#canonicalize)|Этот метод используется для преобразования строки URL-адрес в канонической форме.|  
|[CUrl::Clear](#clear)|Этот метод используется для очистки всех полей URL-адрес.|  
|[CUrl::CrackUrl](#crackurl)|Этот метод вызывается для расшифровки и синтаксический анализ URL-адрес.|  
|[CUrl::CreateUrl](#createurl)|Этот метод используется для создания URL-адрес.|  
|[CUrl::GetExtraInfo](#getextrainfo)|Этот метод вызывается для получения дополнительных сведений (таких как *текст* или # *текст*) по URL-адресу.|  
|[CUrl::GetExtraInfoLength](#getextrainfolength)|Вызовите этот метод, чтобы получить дополнительные сведения (такие как *текст* или # *текст*) для получения URL-адреса.|  
|[CUrl::GetHostName](#gethostname)|Этот метод используется для получения имени узла в URL-адресе.|  
|[CUrl::GetHostNameLength](#gethostnamelength)|Этот метод используется для получения длины имени узла.|  
|[CUrl::GetPassword](#getpassword)|Вызовите этот метод, чтобы получить пароль по URL-адресу.|  
|[CUrl::GetPasswordLength](#getpasswordlength)|Этот метод используется для получения длины пароля.|  
|[CUrl::GetPortNumber](#getportnumber)|Этот метод вызывается для получения номера порта с точки зрения ATL_URL_PORT.|  
|[CUrl::GetScheme](#getscheme)|Вызовите этот метод, чтобы получить схему URL-адрес.|  
|[CUrl::GetSchemeName](#getschemename)|Этот метод используется для получения имени схемы URL-адрес.|  
|[CUrl::GetSchemeNameLength](#getschemenamelength)|Вызовите этот метод, чтобы получить длину имени схемы URL-адрес.|  
|[CUrl::GetUrlLength](#geturllength)|Этот метод используется для получения длина URL-адреса.|  
|[CUrl::GetUrlPath](#geturlpath)|Этот метод используется для получения URL-адрес.|  
|[CUrl::GetUrlPathLength](#geturlpathlength)|Этот метод используется для получения длина пути URL-адреса.|  
|[CUrl::GetUserName](#getusername)|Этот метод вызывается для получения имени пользователя из URL-адрес.|  
|[CUrl::GetUserNameLength](#getusernamelength)|Этот метод используется для получения длины имени пользователя.|  
|[CUrl::SetExtraInfo](#setextrainfo)|Вызовите этот метод для установки дополнительных сведений (таких как *текст* или # *текст*) URL-адреса.|  
|[CUrl::SetHostName](#sethostname)|Этот метод используется для задания имени узла.|  
|[CUrl::SetPassword](#setpassword)|Этот метод позволяет задать пароль.|  
|[CUrl::SetPortNumber](#setportnumber)|Вызовите этот метод, чтобы задать номер порта с точки зрения ATL_URL_PORT.|  
|[CUrl::SetScheme](#setscheme)|Вызовите этот метод, чтобы задать схему URL-адрес.|  
|[CUrl::SetSchemeName](#setschemename)|Этот метод используется для задания имени схемы URL-адрес.|  
|[CUrl::SetUrlPath](#seturlpath)|Этот метод используется для задания URL-адрес.|  
|[CUrl::SetUserName](#setusername)|Этот метод вызывается для задания имени пользователя.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CUrl::operator =](#operator_eq)|Присваивает указанный `CUrl` объект с текущим `CUrl` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CUrl`позволяет управлять поля URL-адрес, например пути или номер порта. `CUrl`принимает URL-адреса следующего вида:  
  
 \<Схема > ://\<имя пользователя >:\<пароль > @\<HostName >:\<номер_порта > /\<UrlPath >\<ExtraInfo >  
  
 (Некоторые поля являются необязательными.) Например рассмотрим этот URL-адрес:  
  
 http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents  
  
 [CUrl::CrackUrl](#crackurl) анализирует его следующим образом:  
  
-   Схема: «http» или [ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)  
  
-   Имя пользователя: «someone»  
  
-   Пароль: «секрет»  
  
-   Имя узла: «www.microsoft.com»  
  
-   PortNumber: 80  
  
-   UrlPath: «visualc/stuff.htm»  
  
-   ExtraInfo: «#contents»  
  
 Чтобы управлять UrlPath поля (например), можно использовать [GetUrlPath](#geturlpath), [GetUrlPathLength](#geturlpathlength), и [SetUrlPath](#seturlpath). Следует использовать [CreateUrl](#createurl) для создания полной строки URL-адрес.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  
  
##  <a name="canonicalize"></a>CUrl::Canonicalize  
 Этот метод используется для преобразования строки URL-адрес в канонической форме.  
  
```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Флаги, управляющие канонизации. Если флаги не заданы ( `dwFlags` = 0), метод преобразует всех небезопасных символов и последовательностей метаданных (например, \\., \.., и \\...) для escape-последовательности. `dwFlags`может принимать одно из следующих значений:  
  
-   ATL_URL_BROWSER_MODE: Не кодирование или декодирование символов после «#» или «» и не удаляет пробелы после «». Если это значение не задано, кодируется весь URL-адрес и удалить конечные пробелы.  
  
-   ATL_URL _DECODE: преобразует все % XX последовательности символов, включая escape-последовательностей, прежде чем разбор URL-адрес.  
  
-   ATL_URL _ENCODE_PERCENT: кодирует все символы процента обнаружил. По умолчанию не кодируются символы процента.  
  
-   ATL_URL _ENCODE_SPACES_ONLY: кодирует только пробелы.  
  
-   ATL_URL _NO_ENCODE: преобразования небезопасных символов в escape-последовательности.  
  
-   ATL_URL _NO_META: не приводит к удалению meta последовательности (такие как «. «и»..») по URL-адресу.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
### <a name="remarks"></a>Примечания  
 Преобразование в канонической форме включает преобразование небезопасных символов и пробелов в escape-последовательности.  
  
##  <a name="clear"></a>CUrl::Clear  
 Этот метод используется для очистки всех полей URL-адрес.  
  
```
inline void Clear() throw();
```  
  
##  <a name="crackurl"></a>CUrl::CrackUrl  
 Этот метод вызывается для расшифровки и синтаксический анализ URL-адрес.  
  
```
BOOL CrackUrl(LPCTSTR lpszUrl, DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszUrl`  
 URL-адрес.  
  
 `dwFlags`  
 Укажите ATL_URL_DECODE или ATL_URL_ESCAPE, чтобы преобразовать все escape-символы в `lpszUrl` реальные значения после синтаксического анализа. (До Visual C++ 2005 ATL_URL_DECODE преобразовать все escape-символы перед синтаксическим анализом.)  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
##  <a name="createurl"></a>CUrl::CreateUrl  
 Этот метод создает строку URL-адрес из поля объект перелистывание компонента.  
  
```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lpszUrl*  
 Строковый буфер для хранения строки полный URL-адрес.  
  
 `pdwMaxLength`  
 Максимальная длина *lpszUrl* строковый буфер.  
  
 `dwFlags`  
 Укажите ATL_URL_ESCAPE для преобразования все escape-символы в *lpszUrl* реальные значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет его отдельные поля для построения полной строки URL-адрес, используя следующий формат:  
  
 **\<Схема > ://\<пользователя >:\<передачи > @\<домена >:\<порт >\<путь >\<лишние >**  
  
 При вызове этого метода `pdwMaxLength` параметр должен содержать изначально Максимальная длина строкового буфера ссылается *lpszUrl* параметра. Значение `pdwMaxLength` обновляется с фактическую длину строки URL-адреса.  
  
### <a name="example"></a>Пример  
 В этом примере демонстрируется создание объекта перелистывание и извлечения его строки URL-адреса  
  
 [!code-cpp[NVC_ATL_Utilities#133](../../atl/codesnippet/cpp/curl-class_1.cpp)]  
  
##  <a name="curl"></a>CUrl::CUrl  
 Конструктор.  
  
```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `urlThat`  
 `CUrl` Объект для копирования для создания URL-адрес.  
  
##  <a name="dtor"></a>CUrl:: ~ CUrl  
 Деструктор  
  
```
~CUrl() throw();
```  
  
##  <a name="getextrainfo"></a>CUrl::GetExtraInfo  
 Этот метод вызывается для получения дополнительных сведений (таких как *текст* или # *текст*) по URL-адресу.  
  
```
inline LPCTSTR GetExtraInfo() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает строку, содержащую Дополнительные сведения.  
  
##  <a name="getextrainfolength"></a>CUrl::GetExtraInfoLength  
 Вызовите этот метод, чтобы получить дополнительные сведения (такие как *текст* или # *текст*) для получения URL-адреса.  
  
```
inline DWORD GetExtraInfoLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает длину строки, содержащее дополнительные сведения.  
  
##  <a name="gethostname"></a>CUrl::GetHostName  
 Этот метод используется для получения имени узла в URL-адресе.  
  
```
inline LPCTSTR GetHostName() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает имя узла.  
  
##  <a name="gethostnamelength"></a>CUrl::GetHostNameLength  
 Этот метод используется для получения длины имени узла.  
  
```
inline DWORD GetHostNameLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает длину имени узла.  
  
##  <a name="getpassword"></a>CUrl::GetPassword  
 Вызовите этот метод, чтобы получить пароль по URL-адресу.  
  
```
inline LPCTSTR GetPassword() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает пароль.  
  
##  <a name="getpasswordlength"></a>CUrl::GetPasswordLength  
 Этот метод используется для получения длины пароля.  
  
```
inline DWORD GetPasswordLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает длину пароля.  
  
##  <a name="getportnumber"></a>CUrl::GetPortNumber  
 Этот метод вызывается для получения номера порта.  
  
```
inline ATL_URL_PORT GetPortNumber() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает номер порта.  
  
##  <a name="getscheme"></a>CUrl::GetScheme  
 Вызовите этот метод, чтобы получить схему URL-адрес.  
  
```
inline ATL_URL_SCHEME GetScheme() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает [ATL_URL_SCHEME](atl-url-scheme-enum.md) значение, описывающее схему URL-адреса.  
  
##  <a name="getschemename"></a>CUrl::GetSchemeName  
 Этот метод используется для получения имени схемы URL-адрес.  
  
```
inline LPCTSTR GetSchemeName() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает имя схемы URL-адрес (например, «http» или «ftp»).  
  
##  <a name="getschemenamelength"></a>CUrl::GetSchemeNameLength  
 Вызовите этот метод, чтобы получить длину имени схемы URL-адрес.  
  
```
inline DWORD GetSchemeNameLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает длину имени схемы URL-адрес.  
  
##  <a name="geturllength"></a>CUrl::GetUrlLength  
 Этот метод используется для получения длина URL-адреса.  
  
```
inline DWORD GetUrlLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает длину URL-адрес.  
  
##  <a name="geturlpath"></a>CUrl::GetUrlPath  
 Этот метод используется для получения URL-адрес.  
  
```
inline LPCTSTR GetUrlPath() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает URL-адрес.  
  
##  <a name="geturlpathlength"></a>CUrl::GetUrlPathLength  
 Этот метод используется для получения длина пути URL-адреса.  
  
```
inline DWORD GetUrlPathLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает длину пути URL-адрес.  
  
##  <a name="getusername"></a>CUrl::GetUserName  
 Этот метод вызывается для получения имени пользователя из URL-адрес.  
  
```
inline LPCTSTR GetUserName() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает имя пользователя.  
  
##  <a name="getusernamelength"></a>CUrl::GetUserNameLength  
 Этот метод используется для получения длины имени пользователя.  
  
```
inline DWORD GetUserNameLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает длину имени пользователя.  
  
##  <a name="operator_eq"></a>CUrl::operator =  
 Присваивает указанный `CUrl` объект с текущим `CUrl` объекта.  
  
```
CUrl& operator= (const CUrl& urlThat) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `urlThat`  
 `CUrl` Объект для копирования в текущий объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на текущий объект.  
  
##  <a name="setextrainfo"></a>CUrl::SetExtraInfo  
 Вызовите этот метод для установки дополнительных сведений (таких как *текст* или # *текст*) URL-адреса.  
  
```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lpszInfo*  
 Строка, содержащая дополнительные сведения, включаемые в URL-адрес.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
##  <a name="sethostname"></a>CUrl::SetHostName  
 Этот метод используется для задания имени узла.  
  
```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszHost`  
 Имя узла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
##  <a name="setpassword"></a>CUrl::SetPassword  
 Этот метод позволяет задать пароль.  
  
```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lpszPass*  
 Пароль.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
##  <a name="setportnumber"></a>CUrl::SetPortNumber  
 Вызовите этот метод, чтобы задать номер порта.  
  
```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *nPrt*  
 Номер порта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
##  <a name="setscheme"></a>CUrl::SetScheme  
 Вызовите этот метод, чтобы задать схему URL-адрес.  
  
```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nScheme`  
 Один из [ATL_URL_SCHEME](atl-url-scheme-enum.md) значения для схемы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
### <a name="remarks"></a>Примечания  
 Можно также задать схему по имени (в разделе [CUrl::SetSchemeName](#setschemename)).  
  
##  <a name="setschemename"></a>CUrl::SetSchemeName  
 Этот метод используется для задания имени схемы URL-адрес.  
  
```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lpszSchm*  
 Имя схемы, URL-адрес.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
### <a name="remarks"></a>Примечания  
 Можно также задать схему с помощью [ATL_URL_SCHEME](atl-url-scheme-enum.md) константы (см. [CUrl::SetScheme](#setscheme)).  
  
##  <a name="seturlpath"></a>CUrl::SetUrlPath  
 Этот метод используется для задания URL-адрес.  
  
```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszPath`  
 URL-адрес.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
##  <a name="setusername"></a>CUrl::SetUserName  
 Этот метод вызывается для задания имени пользователя.  
  
```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lpszUser*  
 Имя пользователя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE при успешном выполнении FALSE в случае ошибки.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../atl/reference/atl-classes.md)
