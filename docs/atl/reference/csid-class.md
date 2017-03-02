---
title: "Класс CSid | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSid
- ATL::CSid
- ATL.CSid
dev_langs:
- C++
helpviewer_keywords:
- CSid class
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
caps.latest.revision: 24
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
ms.openlocfilehash: ceb0ab95d18e1336584eab45bc00ce769efd7384
ms.lasthandoff: 02/24/2017

---
# <a name="csid-class"></a>Идентификатор CSid класса
Этот класс является оболочкой для `SID` структуры (идентификатор безопасности).  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CSid
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSid::CSidArray](#csidarray)|Массив объектов `CSid`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSid::CSid](#csid)|Конструктор.|  
|[Идентификатор CSid:: ~ CSid](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSid::AccountName](#accountname)|Возвращает имя учетной записи, связанной с `CSid` объекта.|  
|[CSid::Domain](#domain)|Возвращает имя домена, связанного с `CSid` объекта.|  
|[CSid::EqualPrefix](#equalprefix)|Тесты `SID` префиксы (идентификатор безопасности) для проверки на равенство.|  
|[CSid::GetLength](#getlength)|Возвращает длину `CSid` объекта.|  
|[CSid::GetPSID](#getpsid)|Возвращает указатель на `SID` структуры.|  
|[CSid::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|Возвращает указатель на **SID_IDENTIFIER_AUTHORITY** структуры.|  
|[CSid::GetSubAuthority](#getsubauthority)|Возвращает указанный полей подчиненного защитного кода в **SID** структуры.|  
|[CSid::GetSubAuthorityCount](#getsubauthoritycount)|Возвращает число полей подчиненного защитного кода.|  
|[CSid::IsValid](#isvalid)|Тесты `CSid` объекта на допустимость.|  
|[CSid::LoadAccount](#loadaccount)|Обновления `CSid` имя учетной записи и домен или существующий объект `SID` структуры.|  
|[CSid::Sid](#sid)|Возвращает строку идентификатора.|  
|[CSid::SidNameUse](#sidnameuse)|Возвращает описание состояния `CSid` объекта.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор =](#operator_eq)|Оператор присвоения.|  
|[оператор const SID *](#operator_const_sid__star)|Приведение `CSid` объекта в указатель `SID` структуры.|  
  
### <a name="global-operators"></a>Глобальные операторы  
  
|||  
|-|-|  
|[оператор ==](#operator_eq_eq)|Проверяет два объекта дескриптора безопасности на равенство|  
|[оператор! =](#operator_neq)|Проверяет два объекта дескриптора безопасности для проверки на неравенство|  
|[оператор\<](#operator_lt_)|Сравнивает относительные значения двух объектов дескриптора безопасности.|  
|[оператор настроек](#operator_gt_)|Сравнивает относительные значения двух объектов дескриптора безопасности.|  
|[оператор\<=](#operator_lt__eq)|Сравнивает относительные значения двух объектов дескриптора безопасности.|  
|[оператор настроек =](#operator_gt__eq)|Сравнивает относительные значения двух объектов дескриптора безопасности.|  
  
## <a name="remarks"></a>Примечания  
 `SID` Структура является структурой переменной длины, используется для идентификации пользователей или групп.  
  
 Не следует изменять приложения `SID` структуры непосредственно, но вместо этого используйте методы, предоставленные в этом классе-оболочке. См. также [AtlGetOwnerSid](http://msdn.microsoft.com/library/0e3a2606-74b8-4412-9803-bb437e22da85), [AtlSetGroupSid](http://msdn.microsoft.com/library/83531d32-11ab-4a68-a3c6-1bfa54ab8dfa), [AtlGetGroupSid](http://msdn.microsoft.com/library/8e7ec6b9-15c8-4a8a-977e-1e4c853d0be7), и [AtlSetOwnerSid](http://msdn.microsoft.com/library/3a8abb76-1d2c-465d-a5e8-62a12a3c37f3).  
  
 Введение в модель управления доступом в Windows см. в разделе [управления доступом](http://msdn.microsoft.com/library/windows/desktop/aa374860) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsecurity.h  
  
##  <a name="a-nameaccountnamea--csidaccountname"></a><a name="accountname"></a>CSid::AccountName  
 Возвращает имя учетной записи, связанной с `CSid` объекта.  
  
```
LPCTSTR AccountName() const throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `LPCTSTR` указывает имя учетной записи.  
  
### <a name="remarks"></a>Примечания  
 Этот метод пытается найти имя для указанного `SID` (идентификатор безопасности). Дополнительные сведения см. [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166).  
  
 Если нет имени учетной записи для `SID` можно найти, `AccountName` возвращает пустую строку. Это может произойти, если время ожидания сети предотвращает определение имени этого метода. Она также происходит идентификаторы безопасности без соответствующего имени учетной записи, таких как вход в систему `SID` , идентифицирующий сеанс входа в систему.  
  
##  <a name="a-namecsida--csidcsid"></a><a name="csid"></a>CSid::CSid  
 Конструктор.  
  
```
CSid() throw();
CSid(const SID& rhs) throw(...);
CSid(const CSid& rhs) throw(...);

CSid(
    const SID_IDENTIFIER_AUTHORITY& IdentifierAuthority,
    BYTE nSubAuthorityCount,
    ...) throw(...);

explicit CSid(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

explicit CSid(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 Существующий `CSid` объекта или `SID` структуры (идентификатор безопасности).  
  
 *IdentifierAuthority*  
 Центр сертификации.  
  
 *nSubAuthorityCount*  
 Число полей подчиненного защитного кода.  
  
 `pszAccountName`  
 Имя учетной записи.  
  
 `pszSystem`  
 Имя системы. Эта строка может быть имя удаленного компьютера. Если значение свойства равно NULL, вместо этого используется локальный компьютер.  
  
 `pSid`  
 Указатель на `SID` структуры.  
  
### <a name="remarks"></a>Примечания  
 Конструктор инициализирует `CSid` объект, значение члена внутренние данные *SidTypeInvalid*, либо скопировав параметры из существующего `CSid`, `SID`, или существующую учетную запись.  
  
 В случае сбоя инициализации конструктор выдаст [CAtlException класса](../../atl/reference/catlexception-class.md).  
  
##  <a name="a-namedtora--csidcsid"></a><a name="dtor"></a>Идентификатор CSid:: ~ CSid  
 Деструктор  
  
```
virtual ~CSid() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Деструктор освобождает все ресурсы, полученные из объекта.  
  
##  <a name="a-namecsidarraya--csidcsidarray"></a><a name="csidarray"></a>CSid::CSidArray  
 Массив [CSid](../../atl/reference/csid-class.md) объектов.  
  
```
typedef CAtlArray<CSid> CSidArray;
```  
  
### <a name="remarks"></a>Примечания  
 Это определение типа задает тип массива, который может использоваться для получения идентификаторов безопасности из списка управления Доступом (access control list). В разделе [CAcl::GetAclEntries](../../atl/reference/cacl-class.md#getaclentries).  
  
##  <a name="a-namedomaina--csiddomain"></a><a name="domain"></a>CSid::Domain  
 Возвращает имя домена, связанного с `CSid` объекта.  
  
```
LPCTSTR Domain() const throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `LPCTSTR` указывает на домен.  
  
### <a name="remarks"></a>Примечания  
 Этот метод пытается найти имя для указанного `SID` (идентификатор безопасности). Дополнительные сведения см. [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166).  
  
 Если нет имени учетной записи для `SID` можно найти, **домена** Возвращает домен как пустая строка. Это может произойти, если время ожидания сети предотвращает определение имени этого метода. Она также происходит идентификаторы безопасности без соответствующего имени учетной записи, таких как вход в систему `SID` , идентифицирующий сеанс входа в систему.  
  
##  <a name="a-nameequalprefixa--csidequalprefix"></a><a name="equalprefix"></a>CSid::EqualPrefix  
 Тесты `SID` префиксы (идентификатор безопасности) для проверки на равенство.  
  
```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 `SID` Структуры (идентификатор безопасности) или `CSid` объект для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** в случае успешного выполнения **false** в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 В разделе [EqualPrefixSid](http://msdn.microsoft.com/library/windows/desktop/aa446621) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительных сведений.  
  
##  <a name="a-namegetlengtha--csidgetlength"></a><a name="getlength"></a>CSid::GetLength  
 Возвращает длину `CSid` объекта.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает длину в байтах `CSid` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если `CSid` имеет недопустимую структуру, возвращаемое значение не определено. Перед вызовом метода `GetLength`, используйте [CSid::IsValid](#isvalid) убедитесь, что функция-член `CSid` является допустимым.  
  
> [!NOTE]
>  В отладочных построениях, функция вызовет метод ASSERT, если `CSid` недопустимый объект.  
  
##  <a name="a-namegetpsida--csidgetpsid"></a><a name="getpsid"></a>CSid::GetPSID  
 Возвращает указатель на `SID` структуры (идентификатор безопасности).  
  
```
const SID* GetPSID() const throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает адрес `CSid` основным `SID` структуры.  
  
##  <a name="a-namegetpsididentifierauthoritya--csidgetpsididentifierauthority"></a><a name="getpsid_identifier_authority"></a>CSid::GetPSID_IDENTIFIER_AUTHORITY  
 Возвращает указатель на **SID_IDENTIFIER_AUTHORITY** структуры.  
  
```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается адрес **SID_IDENTIFIER_AUTHORITY** структуры. В противном случае возвращаемое значение не определено. Сбой может возникать, если `CSid` недопустимый объект, в этом случае [CSid::IsValid](#isvalid) возвращает метод **false**. Функция `GetLastError` может быть вызван для расширенных сведений об ошибках.  
  
> [!NOTE]
>  В отладочных построениях, функция вызовет метод ASSERT, если `CSid` недопустимый объект.  
  
##  <a name="a-namegetsubauthoritya--csidgetsubauthority"></a><a name="getsubauthority"></a>CSid::GetSubAuthority  
 Возвращает указанный полей подчиненного защитного кода в `SID` структуру (идентификатор безопасности).  
  
```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 *nSubAuthority*  
 Данных неверна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает полей подчиненного защитного кода, на который указывает *nSubAuthority.* Значение полей подчиненного защитного кода — относительный идентификатор (RID).  
  
### <a name="remarks"></a>Примечания  
 *NSubAuthority* параметр указывает определение элемента массива данных неверна, метод возвращает значение индекса. Этот метод выполняет проверочные тесты не на это значение. Приложение может вызвать [CSid::GetSubAuthorityCount](#getsubauthoritycount) для обнаружения диапазон допустимых значений.  
  
> [!NOTE]
>  В отладочных построениях, функция вызовет метод ASSERT, если `CSid` недопустимый объект.  
  
##  <a name="a-namegetsubauthoritycounta--csidgetsubauthoritycount"></a><a name="getsubauthoritycount"></a>CSid::GetSubAuthorityCount  
 Возвращает число полей подчиненного защитного кода.  
  
```
UCHAR GetSubAuthorityCount() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если метод завершается успешно, возвращается число полей подчиненного защитного кода.  
  
 При сбое метода, возвращаемое значение не определено. Если происходит сбой метода `CSid` недопустимый объект. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.  
  
> [!NOTE]
>  В отладочных построениях, функция вызовет метод ASSERT, если `CSid` недопустимый объект.  
  
##  <a name="a-nameisvalida--csidisvalid"></a><a name="isvalid"></a>CSid::IsValid  
 Тесты `CSid` объекта на допустимость.  
  
```
bool IsValid() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если `CSid` объект является допустимым, **false** Если нет. Нет информации расширенное сообщение об ошибке для данного метода; не следует вызывать `GetLastError`.  
  
### <a name="remarks"></a>Примечания  
 `IsValid` Проверяет метод `CSid` объекта, проверяя, что номер редакции известных диапазона и что число поля меньше максимального.  
  
##  <a name="a-nameloadaccounta--csidloadaccount"></a><a name="loadaccount"></a>CSid::LoadAccount  
 Обновления `CSid` объекта, имя учетной записи и домен или существующую структуру идентификатор защиты (SID).  
  
```
bool LoadAccount(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

bool LoadAccount(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `pszAccountName`  
 Имя учетной записи.  
  
 `pszSystem`  
 Имя системы. Эта строка может быть имя удаленного компьютера. Если значение свойства равно NULL, вместо этого используется локальный компьютер.  
  
 `pSid`  
 Указатель на [SID](http://msdn.microsoft.com/library/windows/desktop/aa379594\(v=vs.85\).aspx) структуры.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** в случае успешного выполнения **false** в случае сбоя. Чтобы получить расширенные сведения об ошибке, вызовите функцию `GetLastError`.  
  
### <a name="remarks"></a>Примечания  
 `LoadAccount`пытается найти идентификатор безопасности для указанного имени. В разделе [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166\(v=vs.85\).aspx) подробнее.  
  
##  <a name="a-nameoperatoreqa--csidoperator-"></a><a name="operator_eq"></a>CSid::operator =  
 Оператор присвоения.  
  
```
CSid& operator= (const CSid& rhs) throw(...);  
CSid& operator= (const SID& rhs) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `rhs`  
 `SID` (Идентификатор безопасности) или `CSid` для назначения `CSid` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на обновленный `CSid` объекта.  
  
##  <a name="a-nameoperatoreqeqa--csidoperator-"></a><a name="operator_eq_eq"></a>CSid::operator ==  
 Проверяет два объекта дескриптора безопасности для проверки на равенство.  
  
```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 `SID` (Идентификатор безопасности) или `CSid` , отображается в левой части оператора ==.  
  
 `rhs`  
 `SID` (Идентификатор безопасности) или `CSid` , отображается справа от оператора ==.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если дескрипторы безопасности равны; в противном случае **false**.  
  
##  <a name="a-nameoperatorneqa--csidoperator-"></a><a name="operator_neq"></a>CSid::operator! =  
 Проверяет два объекта дескриптора безопасности для проверки на неравенство.  
  
```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 `SID` (Идентификатор безопасности) или `CSid` , отображается в левой части! =-оператор.  
  
 `rhs`  
 `SID` (Идентификатор безопасности) или `CSid` , отображается справа от! =-оператор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если дескрипторы безопасности не равны; в противном случае **false**.  
  
##  <a name="a-nameoperatorlta--csidoperator-lt"></a><a name="operator_lt"></a>CSid::operator&lt;  
 Сравнивает относительные значения двух объектов дескриптора безопасности.  
  
```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 `SID` (Идентификатор безопасности) или `CSid` , отображается в левой части! =-оператор.  
  
 `rhs`  
 `SID` (Идентификатор безопасности) или `CSid` , отображается справа от! =-оператор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если `lhs` — меньше, чем `rhs`, в противном случае **false**.  
  
##  <a name="a-nameoperatorlteqa--csidoperator-lt"></a><a name="operator_lt__eq"></a>CSid::operator&lt;=  
 Сравнивает относительные значения двух объектов дескриптора безопасности.  
  
```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 `SID` (Идентификатор безопасности) или `CSid` , отображается в левой части! =-оператор.  
  
 `rhs`  
 `SID` (Идентификатор безопасности) или `CSid` , отображается справа от! =-оператор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если `lhs` меньше или равно `rhs`, в противном случае **false**.  
  
##  <a name="a-nameoperatorgta--csidoperator-gt"></a><a name="operator_gt"></a>CSid::operator&gt;  
 Сравнивает относительные значения двух объектов дескриптора безопасности.  
  
```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 `SID` (Идентификатор безопасности) или `CSid` , отображается в левой части! =-оператор.  
  
 `rhs`  
 `SID` (Идентификатор безопасности) или `CSid` , отображается справа от! =-оператор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если `lhs` больше, чем `rhs`, в противном случае **false**.  
  
##  <a name="a-nameoperatorgteqa--csidoperator-gt"></a><a name="operator_gt__eq"></a>CSid::operator&gt;=  
 Сравнивает относительные значения двух объектов дескриптора безопасности.  
  
```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```  
  
### <a name="parameters"></a>Параметры  
 `lhs`  
 `SID` (Идентификатор безопасности) или `CSid` , отображается в левой части! =-оператор.  
  
 `rhs`  
 `SID` (Идентификатор безопасности) или `CSid` , отображается справа от! =-оператор.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если `lhs` больше или равен `rhs`, в противном случае **false**.  
  
##  <a name="a-nameoperatorconstsidstara--csidoperator-const-sid-"></a><a name="operator_const_sid__star"></a>CSid::operator const SID *  
 Приведение `CSid` объекта в указатель `SID` структуры (идентификатор безопасности).  
  
```  
operator const SID *() const throw(...);
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает адрес `SID` структуры.  
  
##  <a name="a-namesida--csidsid"></a><a name="sid"></a>CSid::Sid  
 Возвращает `SID` структуры (идентификатор безопасности) как строка.  
  
```
LPCTSTR Sid() const throw(...);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `SID` структуру в виде строки в формате, пригодном для отображения, сохранения или передачи. Эквивалентно [функция ConvertSidToStringSid](http://msdn.microsoft.com/library/windows/desktop/aa376399), несмотря на то, что эта функция только в Windows 2000 и более поздних версиях и чтобы эмулировать операционных систем предыдущих версий.  
  
##  <a name="a-namesidnameusea--csidsidnameuse"></a><a name="sidnameuse"></a>CSid::SidNameUse  
 Возвращает описание состояния `CSid` объекта.  
  
```
SID_NAME_USE SidNameUse() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение элемента данных, который хранит значение, описывающее состояние `CSid` объекта.  
  
|Значение|Описание|  
|-----------|-----------------|  
|SidTypeUser|Указывает пользователя `SID` (идентификатор безопасности).|  
|SidTypeGroup|Указывает группу `SID`.|  
|SidTypeDomain|Указывает домен `SID`.|  
|SidTypeAlias|Указывает псевдоним `SID`.|  
|SidTypeWellKnownGroup|Указывает `SID` для хорошо известная группа.|  
|SidTypeDeletedAccount|Указывает `SID` для удаленной учетной записи.|  
|SidTypeInvalid|Указывает на недопустимый `SID`.|  
|SidTypeUnknown|Указывает Неизвестный `SID` типа.|  
|SidTypeComputer|Указывает `SID` для компьютера.|  
  
### <a name="remarks"></a>Примечания  
 Вызов [CSid::LoadAccount](#loadaccount) обновление `CSid` объект перед вызовом метода `SidNameUse` для возврата состояния. `SidNameUse`не изменяет состояние объекта (путем вызова **LookupAccountName** или **LookupAccountSid**), но только возвращает текущее состояние.  
  
## <a name="see-also"></a>См. также  
 [Образец безопасности](../../visual-cpp-samples.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Глобальные функции безопасности](../../atl/reference/security-global-functions.md)   
 [Операторы](../../atl/reference/atl-operators.md)

