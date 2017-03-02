---
title: "Переворачивание класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CUrl
- CUrl
- ATL::CUrl
dev_langs:
- C++
helpviewer_keywords:
- CUrl class
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
caps.latest.revision: 22
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: eda63a8dc704dd471d8078b848d95fc9fb44f58f
ms.lasthandoff: 02/24/2017

---
# <a name="curl-class"></a>Переворачивание класса
Этот класс представляет URL-адрес. Он позволяет управлять каждый элемент URL-адрес, независимо от других ли синтаксического анализа URL-адрес существующей строки или создание строки с нуля.  
  
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
|[Переворачивание:: ~ переворачивание](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CUrl::Canonicalize](#canonicalize)|Этот метод используется для преобразования строки URL-адреса в каноническую форму.|  
|[CUrl::Clear](#clear)|Вызовите этот метод, чтобы удалить все поля URL-адрес.|  
|[CUrl::CrackUrl](#crackurl)|Этот метод вызывается для расшифровки и синтаксического анализа URL-адрес.|  
|[CUrl::CreateUrl](#createurl)|Этот метод используется для создания URL-адрес.|  
|[CUrl::GetExtraInfo](#getextrainfo)|Этот метод вызывается для получения дополнительной информации (такие как *текст* или # *текст*) по URL-адресу.|  
|[CUrl::GetExtraInfoLength](#getextrainfolength)|Вызовите этот метод, чтобы получить дополнительные сведения (такие как *текст* или # *текст*) для получения URL-адреса.|  
|[CUrl::GetHostName](#gethostname)|Этот метод используется для получения имени узла URL-адреса.|  
|[CUrl::GetHostNameLength](#gethostnamelength)|Этот метод используется для получения длины имени узла.|  
|[CUrl::GetPassword](#getpassword)|Этот метод используется для получения пароля по URL-адресу.|  
|[CUrl::GetPasswordLength](#getpasswordlength)|Этот метод используется для получения длины пароля.|  
|[CUrl::GetPortNumber](#getportnumber)|Этот метод вызывается для получения номера порта, с точки зрения ATL_URL_PORT.|  
|[CUrl::GetScheme](#getscheme)|Вызовите этот метод, чтобы получить схему URL-адрес.|  
|[CUrl::GetSchemeName](#getschemename)|Этот метод используется для получения имени схемы URL-адрес.|  
|[CUrl::GetSchemeNameLength](#getschemenamelength)|Вызовите этот метод, чтобы получить имя схемы URL-адрес.|  
|[CUrl::GetUrlLength](#geturllength)|Этот метод используется для получения длины URL-адрес.|  
|[CUrl::GetUrlPath](#geturlpath)|Вызовите этот метод для получения URL-адрес.|  
|[CUrl::GetUrlPathLength](#geturlpathlength)|Этот метод используется для получения длины пути URL-адреса.|  
|[CUrl::GetUserName](#getusername)|Этот метод вызывается для получения имени пользователя из URL-адреса.|  
|[CUrl::GetUserNameLength](#getusernamelength)|Этот метод используется для получения длины имени пользователя.|  
|[CUrl::SetExtraInfo](#setextrainfo)|Вызовите этот метод, чтобы задать дополнительные сведения (такие как *текст* или # *текст*) URL-адреса.|  
|[CUrl::SetHostName](#sethostname)|Этот метод служит для задания имени узла.|  
|[CUrl::SetPassword](#setpassword)|Вызовите этот метод, чтобы задать пароль.|  
|[CUrl::SetPortNumber](#setportnumber)|Вызовите этот метод, чтобы задать номер порта, с точки зрения ATL_URL_PORT.|  
|[CUrl::SetScheme](#setscheme)|Вызовите этот метод, чтобы задать схему URL-адрес.|  
|[CUrl::SetSchemeName](#setschemename)|Вызовите этот метод, чтобы задать имя схемы URL-адрес.|  
|[CUrl::SetUrlPath](#seturlpath)|Вызовите этот метод, чтобы задать URL-адрес.|  
|[CUrl::SetUserName](#setusername)|Этот метод вызывается для задания имени пользователя.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CUrl::operator =](#operator_eq)|Присваивает указанный `CUrl` объект с текущим `CUrl` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CUrl`позволяет управлять поля URL-адрес, например пути или номер порта. `CUrl`принимает URL-адреса следующего вида:  
  
 \<Схема настроек: или или\<UserName настроек:\<пароль настроек @\<имя узла настроек:\<номер_порта настроек и\<UrlPath настроек\<ExtraInfo настроек  
  
 (Некоторые поля являются обязательными). Например рассмотрим этот URL-адрес:  
  
 http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents  
  
 [CUrl::CrackUrl](#crackurl) анализирует его следующим образом:  
  
-   Схема: «http» или [ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)  
  
-   Имя пользователя: «пользователь»  
  
-   Пароль: секретный «код»  
  
-   Имя узла: «www.microsoft.com»  
  
-   Номер_порта: 80  
  
-   UrlPath: «visualc/stuff.htm»  
  
-   ExtraInfo: «#contents»  
  
 Для управления UrlPath поля (например), используйте [GetUrlPath](#geturlpath), [GetUrlPathLength](#geturlpathlength), и [SetUrlPath](#seturlpath). Следует использовать [CreateUrl](#createurl) для создания полной строки URL-адреса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  
  
##  <a name="a-namecanonicalizea--curlcanonicalize"></a><a name="canonicalize"></a>CUrl::Canonicalize  
 Этот метод используется для преобразования строки URL-адреса в каноническую форму.  
  
```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Флаги, которые управляют канонизации. Если флаги не заданы ( `dwFlags` = 0), этот метод преобразует все небезопасные символы и последовательностей meta (такие как \\., \.., и \\...) в escape-последовательности. `dwFlags`может принимать одно из следующих значений:  
  
-   ATL_URL_BROWSER_MODE: Не закодировать или декодировать знаки после «#» или «» и не удаляет пробелы после «». Если это значение не задано, кодируется весь URL-адрес и конечные пробелы удаляются.  
  
-   ATL_URL _DECODE: преобразует все % XX последовательности символов, включая escape-последовательности, прежде чем разбор URL-адрес.  
  
-   ATL_URL _ENCODE_PERCENT: кодирует все символы процента обнаружил. По умолчанию символы процента не кодируются.  
  
-   ATL_URL _ENCODE_SPACES_ONLY: кодирует только пробелы.  
  
-   ATL_URL _NO_ENCODE: преобразования небезопасных символов в escape-последовательности.  
  
-   ATL_URL _NO_META: не удаляет meta последовательности (такие как». «и»..») из URL-адреса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Преобразование в канонической форме включает преобразование небезопасных символов и пробелов в escape-последовательности.  
  
##  <a name="a-namecleara--curlclear"></a><a name="clear"></a>CUrl::Clear  
 Вызовите этот метод, чтобы удалить все поля URL-адрес.  
  
```
inline void Clear() throw();
```  
  
##  <a name="a-namecrackurla--curlcrackurl"></a><a name="crackurl"></a>CUrl::CrackUrl  
 Этот метод вызывается для расшифровки и синтаксического анализа URL-адрес.  
  
```
BOOL CrackUrl(LPCTSTR lpszUrl, DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszUrl`  
 URL-адрес.  
  
 `dwFlags`  
 Укажите ATL_URL_DECODE или ATL_URL_ESCAPE, чтобы преобразовать все escape-символы в `lpszUrl` реальные значения после синтаксического анализа. (До Visual C++ 2005 ATL_URL_DECODE преобразовать все escape-символы перед анализом.)  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
##  <a name="a-namecreateurla--curlcreateurl"></a><a name="createurl"></a>CUrl::CreateUrl  
 Этот метод создает строку URL-адрес из поля объект перелистывание компонентов.  
  
```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lpszUrl*  
 Строка буфера для хранения строки полный URL-адрес.  
  
 `pdwMaxLength`  
 Максимальная длина *lpszUrl* буфера строки.  
  
 `dwFlags`  
 Укажите ATL_URL_ESCAPE для преобразования всех escape-символы в *lpszUrl* реальные значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод добавляет его отдельные поля для создания полной строки URL-адрес, используя следующий формат:  
  
 **\<Схема настроек: или или\<пользователя настроек:\<передачи настроек @\<домена настроек:\<порт настроек\<путь настроек\<дополнительных настроек**  
  
 При вызове этого метода `pdwMaxLength` параметр должен содержать изначально Максимальная длина буфера строки ссылается *lpszUrl* параметр. Значение `pdwMaxLength` обновляется с фактической длины строки URL-адреса.  
  
### <a name="example"></a>Пример  
 В этом примере демонстрируется создание объекта перелистывание и извлечения его строки URL-адреса  
  
 [!code-cpp[NVC_ATL_Utilities&#133;](../../atl/codesnippet/cpp/curl-class_1.cpp)]  
  
##  <a name="a-namecurla--curlcurl"></a><a name="curl"></a>CUrl::CUrl  
 Конструктор.  
  
```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `urlThat`  
 `CUrl` , Который копируется для создания URL-адрес.  
  
##  <a name="a-namedtora--curlcurl"></a><a name="dtor"></a>Переворачивание:: ~ переворачивание  
 Деструктор  
  
```
~CUrl() throw();
```  
  
##  <a name="a-namegetextrainfoa--curlgetextrainfo"></a><a name="getextrainfo"></a>CUrl::GetExtraInfo  
 Этот метод вызывается для получения дополнительной информации (такие как *текст* или # *текст*) по URL-адресу.  
  
```
inline LPCTSTR GetExtraInfo() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает строку, содержащую Дополнительные сведения.  
  
##  <a name="a-namegetextrainfolengtha--curlgetextrainfolength"></a><a name="getextrainfolength"></a>CUrl::GetExtraInfoLength  
 Вызовите этот метод, чтобы получить дополнительные сведения (такие как *текст* или # *текст*) для получения URL-адреса.  
  
```
inline DWORD GetExtraInfoLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает длину строки, содержащее дополнительные сведения.  
  
##  <a name="a-namegethostnamea--curlgethostname"></a><a name="gethostname"></a>CUrl::GetHostName  
 Этот метод используется для получения имени узла URL-адреса.  
  
```
inline LPCTSTR GetHostName() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает имя узла.  
  
##  <a name="a-namegethostnamelengtha--curlgethostnamelength"></a><a name="gethostnamelength"></a>CUrl::GetHostNameLength  
 Этот метод используется для получения длины имени узла.  
  
```
inline DWORD GetHostNameLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает длину имени узла.  
  
##  <a name="a-namegetpassworda--curlgetpassword"></a><a name="getpassword"></a>CUrl::GetPassword  
 Этот метод используется для получения пароля по URL-адресу.  
  
```
inline LPCTSTR GetPassword() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает пароль.  
  
##  <a name="a-namegetpasswordlengtha--curlgetpasswordlength"></a><a name="getpasswordlength"></a>CUrl::GetPasswordLength  
 Этот метод используется для получения длины пароля.  
  
```
inline DWORD GetPasswordLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает длину пароля.  
  
##  <a name="a-namegetportnumbera--curlgetportnumber"></a><a name="getportnumber"></a>CUrl::GetPortNumber  
 Этот метод вызывается для получения номера порта.  
  
```
inline ATL_URL_PORT GetPortNumber() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает номер порта.  
  
##  <a name="a-namegetschemea--curlgetscheme"></a><a name="getscheme"></a>CUrl::GetScheme  
 Вызовите этот метод, чтобы получить схему URL-адрес.  
  
```
inline ATL_URL_SCHEME GetScheme() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает [ATL_URL_SCHEME](atl-url-scheme-enum.md) значение, описывающее схему URL-адреса.  
  
##  <a name="a-namegetschemenamea--curlgetschemename"></a><a name="getschemename"></a>CUrl::GetSchemeName  
 Этот метод используется для получения имени схемы URL-адрес.  
  
```
inline LPCTSTR GetSchemeName() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает имя схемы URL-адрес (например, «http» или «ftp»).  
  
##  <a name="a-namegetschemenamelengtha--curlgetschemenamelength"></a><a name="getschemenamelength"></a>CUrl::GetSchemeNameLength  
 Вызовите этот метод, чтобы получить имя схемы URL-адрес.  
  
```
inline DWORD GetSchemeNameLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает URL-адрес, длина имени схемы.  
  
##  <a name="a-namegeturllengtha--curlgeturllength"></a><a name="geturllength"></a>CUrl::GetUrlLength  
 Этот метод используется для получения длины URL-адрес.  
  
```
inline DWORD GetUrlLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает длину URL-адрес.  
  
##  <a name="a-namegeturlpatha--curlgeturlpath"></a><a name="geturlpath"></a>CUrl::GetUrlPath  
 Вызовите этот метод для получения URL-адрес.  
  
```
inline LPCTSTR GetUrlPath() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает URL-адрес.  
  
##  <a name="a-namegeturlpathlengtha--curlgeturlpathlength"></a><a name="geturlpathlength"></a>CUrl::GetUrlPathLength  
 Этот метод используется для получения длины пути URL-адреса.  
  
```
inline DWORD GetUrlPathLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает длину пути URL-адреса.  
  
##  <a name="a-namegetusernamea--curlgetusername"></a><a name="getusername"></a>CUrl::GetUserName  
 Этот метод вызывается для получения имени пользователя из URL-адреса.  
  
```
inline LPCTSTR GetUserName() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает имя пользователя.  
  
##  <a name="a-namegetusernamelengtha--curlgetusernamelength"></a><a name="getusernamelength"></a>CUrl::GetUserNameLength  
 Этот метод используется для получения длины имени пользователя.  
  
```
inline DWORD GetUserNameLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает длину имени пользователя.  
  
##  <a name="a-nameoperatoreqa--curloperator-"></a><a name="operator_eq"></a>CUrl::operator =  
 Присваивает указанный `CUrl` объект с текущим `CUrl` объекта.  
  
```
CUrl& operator= (const CUrl& urlThat) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `urlThat`  
 `CUrl` Объект для копирования в текущий объект.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на текущий объект.  
  
##  <a name="a-namesetextrainfoa--curlsetextrainfo"></a><a name="setextrainfo"></a>CUrl::SetExtraInfo  
 Вызовите этот метод, чтобы задать дополнительные сведения (такие как *текст* или # *текст*) URL-адреса.  
  
```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lpszInfo*  
 Строка, содержащая дополнительные сведения для включения в URL-адрес.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
##  <a name="a-namesethostnamea--curlsethostname"></a><a name="sethostname"></a>CUrl::SetHostName  
 Этот метод служит для задания имени узла.  
  
```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszHost`  
 Имя узла.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
##  <a name="a-namesetpassworda--curlsetpassword"></a><a name="setpassword"></a>CUrl::SetPassword  
 Вызовите этот метод, чтобы задать пароль.  
  
```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lpszPass*  
 Пароль.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
##  <a name="a-namesetportnumbera--curlsetportnumber"></a><a name="setportnumber"></a>CUrl::SetPortNumber  
 Вызовите этот метод, чтобы задать номер порта.  
  
```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *nPrt*  
 Номер порта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
##  <a name="a-namesetschemea--curlsetscheme"></a><a name="setscheme"></a>CUrl::SetScheme  
 Вызовите этот метод, чтобы задать схему URL-адрес.  
  
```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nScheme`  
 Один из [ATL_URL_SCHEME](atl-url-scheme-enum.md) значения для схемы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Можно также задать схему по имени (см. [CUrl::SetSchemeName](#setschemename)).  
  
##  <a name="a-namesetschemenamea--curlsetschemename"></a><a name="setschemename"></a>CUrl::SetSchemeName  
 Вызовите этот метод, чтобы задать имя схемы URL-адрес.  
  
```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lpszSchm*  
 Имя схемы, URL-адрес.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Можно также задать схему с помощью [ATL_URL_SCHEME](atl-url-scheme-enum.md) констант (см. [CUrl::SetScheme](#setscheme)).  
  
##  <a name="a-nameseturlpatha--curlseturlpath"></a><a name="seturlpath"></a>CUrl::SetUrlPath  
 Вызовите этот метод, чтобы задать URL-адрес.  
  
```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lpszPath`  
 URL-адрес.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
##  <a name="a-namesetusernamea--curlsetusername"></a><a name="setusername"></a>CUrl::SetUserName  
 Этот метод вызывается для задания имени пользователя.  
  
```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *lpszUser*  
 Имя пользователя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, операция выполнена успешно; значение FALSE в случае сбоя.  
  
## <a name="see-also"></a>См. также  
 [Классы](../../atl/reference/atl-classes.md)

