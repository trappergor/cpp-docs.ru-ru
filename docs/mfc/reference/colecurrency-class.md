---
title: Класс COleCurrency | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleCurrency
- AFXDISP/COleCurrency
- AFXDISP/COleCurrency::COleCurrency
- AFXDISP/COleCurrency::Format
- AFXDISP/COleCurrency::GetStatus
- AFXDISP/COleCurrency::ParseCurrency
- AFXDISP/COleCurrency::SetCurrency
- AFXDISP/COleCurrency::SetStatus
- AFXDISP/COleCurrency::m_cur
- AFXDISP/COleCurrency::m_status
dev_langs:
- C++
helpviewer_keywords:
- COleCurrency [MFC], COleCurrency
- COleCurrency [MFC], Format
- COleCurrency [MFC], GetStatus
- COleCurrency [MFC], ParseCurrency
- COleCurrency [MFC], SetCurrency
- COleCurrency [MFC], SetStatus
- COleCurrency [MFC], m_cur
- COleCurrency [MFC], m_status
ms.assetid: 3a36e345-303f-46fb-a57c-858274378a8d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1077a9567509d98b68a864d7478ab84b94d11054
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2018
ms.locfileid: "42541506"
---
# <a name="colecurrency-class"></a>Класс COleCurrency
Инкапсулирует тип данных `CURRENCY` автоматизации OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleCurrency  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleCurrency::COleCurrency](#colecurrency)|Создает объект `COleCurrency`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleCurrency::Format](#format)|Создает форматированное строковое представление `COleCurrency` объекта.|  
|[COleCurrency::GetStatus](#getstatus)|Получает состояние (действия) это `COleCurrency` объекта.|  
|[COleCurrency::ParseCurrency](#parsecurrency)|Считывает значение валюты из строки и задает значение `COleCurrency`.|  
|[COleCurrency::SetCurrency](#setcurrency)|Задает значение данного объекта `COleCurrency` объекта.|  
|[COleCurrency::SetStatus](#setstatus)|Задает состояние (действия) для данного `COleCurrency` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[оператор =](#operator_eq)|Копирует `COleCurrency` значение.|  
|[оператор +, -](#operator_plus_minus)|Добавляет, вычитает и изменяет знак `COleCurrency` значения.|  
|[оператор +=-=](#operator_plus_minus_eq)|Добавляет и вычитает `COleCurrency` значение из этого `COleCurrency` объекта.|  
|[оператор * /](#operator_star)|Масштабирует `COleCurrency` значение целое значение.|  
|[оператор * =, / =](#operator_star_div_eq)|Масштабирует эту структуру `COleCurrency` значение целое значение.|  
|[оператор <<](#operator_stream)|Выходные данные `COleCurrency` значение `CArchive` или `CDumpContext`.|  
|[оператор >>](#operator_stream)|Входные данные `COleCurrency` объекта из `CArchive`.|  
|[оператор валюты](#operator_currency)|Преобразует `COleCurrency` значение в ВАЛЮТУ.|  
|[оператор ==, <, < = и т. д.](#colecurrency_relational_operators)|Сравнивает два `COleCurrency` значения.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleCurrency::m_cur](#m_cur)|Содержит основной валюты для данного `COleCurrency` объекта.|  
|[COleCurrency::m_status](#m_status)|Содержит состояние данного объекта `COleCurrency` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `COleCurrency` не имеет базового класса.  
  
 ВАЛЮТА реализовано в виде 8-байтовую, дополнительном целочисленное значение, умноженного на 10000. Это позволяет получить число с фиксированной запятой с 15 разрядами слева от десятичной запятой и 4 разрядами справа от нее. Тип данных CURRENCY очень полезно для денежных расчетов или любые вычисления с фиксированной запятой когда важна точность. Это одна из возможных типов для `VARIANT` тип данных OLE-автоматизации.  
  
 `COleCurrency` также реализует некоторые основные арифметические операции, для этого типа с фиксированной запятой. Поддерживаемые операции были выбраны для управления ошибками округления, которые происходят во время вычислений с фиксированной запятой.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `COleCurrency`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
##  <a name="colecurrency"></a>  COleCurrency::COleCurrency  
 Создает объект `COleCurrency`.  
  
```  
COleCurrency();  
COleCurrency(CURRENCY cySrc);  
  COleCurrency(const COleCurrency& curSrc);  
COleCurrency(const VARIANT& varSrc);

 
COleCurrency(
    long nUnits,  
    long nFractionalUnits);
```  
  
### <a name="parameters"></a>Параметры  
 *cySrc*  
 Значение валюты, который необходимо скопировать в новый `COleCurrency` объекта.  
  
 *curSrc*  
 Существующий `COleCurrency` объект, который необходимо скопировать в новый `COleCurrency` объекта.  
  
 *varSrc*  
 Существующий `VARIANT` структуры данных (возможно `COleVariant` объекта) преобразовывается в виде денежного значения (VT_CY) и скопировать в новый `COleCurrency` объекта.  
  
 *nUnits*, *nFractionalUnits*  
 Указывает количество единиц и дробная часть значения (в 1/десятках тысяч), чтобы скопировать в новый `COleCurrency` объекта.  
  
### <a name="remarks"></a>Примечания  
 Все эти конструкторы создают новые `COleCurrency` объекты, инициализированные указанное значение. Следует краткое описание каждого из этих конструкторов. Если не указано иное состояние нового `COleCurrency` элемента имеет значение на допустимое.  
  
- Конструкции COleCurrency() `COleCurrency` объект инициализируется значением 0 (ноль).  
  
- COleCurrency (`cySrc`) создает `COleCurrency` объекта из [валюты](http://msdn.microsoft.com/5e81273c-7289-45c7-93c0-32c1553f708e) значение.  
  
- COleCurrency (`curSrc`) создает `COleCurrency` из существующего `COleCurrency` объекта. Новый объект имеет такое же состояние, что и исходный объект.  
  
- COleCurrency (`varSrc`) создает `COleCurrency` объекта. Пытается преобразовать [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) структуры или `COleVariant` в значение валюты (VT_CY). Если это преобразование выполнено успешно, преобразованное значение копируется в новый `COleCurrency` объекта. Если это не так, значение `COleCurrency` объекта имеет значение ноль (0) и его состояние на недопустимый.  
  
- `COleCurrency(`nUnits`, `nFractionalUnits`) Constructs a `COleCurrency "объект из указанного числовых компонента. Если абсолютное значение дробной части больше 10 000, соответствующих настроек к единицам. Обратите внимание на то, что единицы и дробной части задаются значения со знаком длинное.  
  
 Дополнительные сведения см. в разделе [валюты](http://msdn.microsoft.com/5e81273c-7289-45c7-93c0-32c1553f708e) и [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) записей в пакете Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующих примерах показано влияние конструкторы нулевой параметр и два параметра:  
  
 [!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]  
  
##  <a name="format"></a>  COleCurrency::Format  
 Эта функция члена для создания отформатированное представление значения валюты.  
  
```  
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const; 
```  
  
### <a name="parameters"></a>Параметры  
 *dwFlags*  
 Указывает флаги для параметров языкового стандарта. Только следующий флаг относится к валюты:  
  
- LOCALE_NOUSEROVERRIDE использовать параметры языкового стандарта системы по умолчанию, а не пользовательские параметры пользователя.  
  
 *lcid*  
 Указывает идентификатор языкового стандарта для использования для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий отформатированного денежного значения.  
  
### <a name="remarks"></a>Примечания  
 Он форматирует значение, используя спецификации местном языке (идентификаторы языковых стандартов). Символ валюты не включается в возвращаемом значении. Если состояние данного объекта `COleCurrency` объект имеет значение null, возвращаемое значение является пустой строкой. Если состояние является недопустимым, возвращаемая строка определяется строковый ресурс IDS_INVALID_CURRENCY.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]  
  
##  <a name="getstatus"></a>  COleCurrency::GetStatus  
 Вызов этой функции-члена для получения состояния (действия) заданного `COleCurrency` объекта.  
  
```  
CurrencyStatus GetStatus() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает состояние данного объекта `COleCurrency` значение.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение определяется `CurrencyStatus` перечислимый тип, в котором определен `COleCurrency` класса.  
  
```  
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };  
```  
  
 Краткое описание этих значений состояния см. в следующем списке:  
  
  - `COleCurrency::valid` Указывает, что этот `COleCurrency` объект является допустимым.  
  
  - `COleCurrency::invalid` Указывает, что этот `COleCurrency` объекта является недопустимым; то есть его значение может быть неправильным.  
  
  - `COleCurrency::null` Указывает, что этот `COleCurrency` объект имеет значение null, то есть, что значение не указано для этого объекта. (Это «null» в смысле «предложений having без значения,» в отличие от C++ NULL базы данных.)  
  
 Состояние `COleCurrency` становится недействительным в следующих случаях:  
  
-   Если он имеет значение из типа VARIANT или `COleVariant` значения, которые не могут быть преобразованы в виде денежного значения.  
  
-   Если этот объект опыт работы с переполнения или потери значимости во время назначения, арифметические операции, например `+=` или **\* =**.  
  
-   Если недопустимое значение был назначен этот объект.  
  
-   Если состояние этого объекта было задано явно недопустимыми с помощью [SetStatus](#setstatus).  
  
 Дополнительные сведения об операциях, которые может присвоить состояние недопустимый см. в следующих функций-членов:  
  
 - [COleCurrency](#colecurrency)  
  
 - [оператор =](#operator_eq)  
  
 - [оператор + -](#operator_plus_minus)  
  
 - [оператор += и-=](#operator_plus_minus_eq)  
  
 - [оператор * /](#operator_star)  
  
 - [оператор * = и / =](#operator_star_div_eq)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]  
  
##  <a name="m_cur"></a>  COleCurrency::m_cur  
 Базовый [валюты](http://msdn.microsoft.com/5e81273c-7289-45c7-93c0-32c1553f708e) структуры для этого `COleCurrency` объекта.  
  
### <a name="remarks"></a>Примечания  
  
> [!CAUTION]
>  Изменение значения в `CURRENCY` структуры осуществляется указатель, возвращаемый этой функцией изменится значение этой `COleCurrency` объекта. Это не приводит к изменению состояния этого `COleCurrency` объекта.  
  
 Дополнительные сведения см. в разделе [валюты](http://msdn.microsoft.com/5e81273c-7289-45c7-93c0-32c1553f708e) запись в пакете Windows SDK.  
  
##  <a name="m_status"></a>  COleCurrency::m_status  
 Тип этого элемента данных является перечисляемым типом `CurrencyStatus`, который определен в `COleCurrency` класса.  
  
```  
enum CurrencyStatus{  
    valid = 0,  
    invalid = 1,  
    null = 2,  
};  
```  
  
### <a name="remarks"></a>Примечания  
Краткое описание этих значений состояния см. в следующем списке:  
  
 - `COleCurrency::valid` Указывает, что этот `COleCurrency` объект является допустимым.  
      
 - `COleCurrency::invalid` Указывает, что этот `COleCurrency` объекта является недопустимым; то есть его значение может быть неправильным.  
      
 - `COleCurrency::null` Указывает, что этот `COleCurrency` объект имеет значение null, то есть, что значение не указано для этого объекта. (Это «null» в смысле «предложений having без значения,» в отличие от C++ NULL базы данных.)  
  
Состояние `COleCurrency` становится недействительным в следующих случаях:  
  
 - Если он имеет значение из типа VARIANT или `COleVariant` значения, которые не могут быть преобразованы в виде денежного значения.  
      
 - Если этот объект опыт работы с переполнения или потери значимости во время назначения, арифметические операции, например `+=` или **\* =**.  
      
 - Если недопустимое значение был назначен этот объект.  
      
 - Если состояние этого объекта было задано явно недопустимыми с помощью [SetStatus](#setstatus).  
  
Дополнительные сведения об операциях, которые может присвоить состояние недопустимый см. в следующих функций-членов:  
  
 - [COleCurrency](#colecurrency)  
      
 - [оператор =](#operator_eq)  
      
 - [оператор +, -](#operator_plus_minus)  
      
 - [оператор +=-=](#operator_plus_minus_eq)  
      
 - [оператор * /](#operator_star)  
      
 - [оператор * =, / =](#operator_star_div_eq)  
  
> [!CAUTION]
>  Этот член данных — для сложных ситуациях программирования. Следует использовать подставляемые функции-члены [GetStatus](#getstatus) и [SetStatus](#setstatus). См. в разделе `SetStatus` дополнительные предупреждения, касающиеся явного задания для этого элемента данных.  
  
##  <a name="operator_eq"></a>  COleCurrency::operator =  
 Эти перегруженных операторах присваивания копирования исходного значения валюты в данный `COleCurrency` объекта.  
  
```  
const COleCurrency& operator=(CURRENCY cySrc);  
const COleCurrency& operator=(const COleCurrency& curSrc);  
  const COleCurrency& operator=(const VARIANT& varSrc);
```  
  
### <a name="remarks"></a>Примечания  
 Краткое описание каждого оператора выглядит следующим образом:  
  
- **оператор = (** `cySrc` **)** `CURRENCY` значение копируется в `COleCurrency` объекта и его состояние имеет значение на допустимое.  
  
- **оператор = (** `curSrc` **)** значение и состояния операнда, существующий `COleCurrency` объект копируются в это `COleCurrency` объекта.  
  
- **оператор = (** *varSrc* **)** Если преобразование `VARIANT` значение (или [COleVariant](../../mfc/reference/colevariant-class.md) объект) для валюты ( `VT_CY`) — в случае успешного выполнения преобразованное значение копируется в этот `COleCurrency` объекта и его состояние имеет значение на допустимое. Если преобразование не выполнено успешно, значение `COleCurrency` объект имеет значение 0, а его состояние на недопустимый.  
  
 Дополнительные сведения см. в разделе [валюты](http://msdn.microsoft.com/5e81273c-7289-45c7-93c0-32c1553f708e) и [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) записей в пакете Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]  
  
##  <a name="operator_plus_minus"></a>  COleCurrency::operator +, -  
 Эти операторы позволяют добавлять и вычитать два `COleCurrency` значениями друг от друга и изменить знак `COleCurrency` значение.  
  
```  
COleCurrency operator+(const COleCurrency& cur) const;  
COleCurrency operator-(const COleCurrency& cur) const;  
COleCurrency operator-() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Если любой из операндов имеет значение null, состояние результата `COleCurrency` имеет значение null.  
  
 Если арифметическая операция переполняет, полученный в результате `COleCurrency` недопустимое значение.  
  
 Если операнд имеет недопустимый, а другой — это не равно null, состояние результата `COleCurrency` недопустимое значение.  
  
 Дополнительные сведения о значениях состояния допустимым, недопустимым и null см. в разделе [m_status](#m_status) переменной-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]  
  
##  <a name="operator_plus_minus_eq"></a>  COleCurrency::operator +=-=  
 Позволяют сложения и вычитания `COleCurrency` значение в и из этого `COleCurrency` объекта.  
  
```  
const COleCurrency& operator+=(const COleCurrency& cur);  
const COleCurrency& operator-=(const COleCurrency& cur);
```  
  
### <a name="remarks"></a>Примечания  
 Если любой из операндов имеет значение null, состояние данного объекта `COleCurrency` объекта задано значение null.  
  
 При переполнении в арифметической операции, состояние данного объекта `COleCurrency` является недопустимым.  
  
 Если любой из операндов является недопустимым, и другой не равно null, состояние данного объекта `COleCurrency` объекта задано на недопустимый.  
  
 Дополнительные сведения о значениях состояния допустимым, недопустимым и null см. в разделе [m_status](#m_status) переменной-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]  
  
##  <a name="operator_star"></a>  COleCurrency::operator \* и /  
 Можно масштабировать `COleCurrency` значение с целочисленным значением.  
  
```  
COleCurrency operator*(long nOperand) const;  
COleCurrency operator/(long nOperand) const;  
```  
  
### <a name="remarks"></a>Примечания  
 Если `COleCurrency` операнд имеет значение null, состояние результата `COleCurrency` имеет значение null.  
  
 При переполнении в арифметической операции или потеря значимости, полученный в результате состояние `COleCurrency` недопустимое значение.  
  
 Если `COleCurrency` операнд является недопустимым, полученный в результате состояние `COleCurrency` недопустимое значение.  
  
 Дополнительные сведения о значениях состояния допустимым, недопустимым и null см. в разделе [m_status](#m_status) переменной-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]  
  
##  <a name="operator_star_div_eq"></a>  COleCurrency::operator \*=, / =  
 Можно масштабировать это `COleCurrency` значение с целочисленным значением.  
  
```  
const COleCurrency& operator*=(long nOperand);  
const COleCurrency& operator/=(long nOperand);
```  
  
### <a name="remarks"></a>Примечания  
 Если `COleCurrency` операнд имеет значение null, состояние данного объекта `COleCurrency` объекта задано значение null.  
  
 При переполнении в арифметической операции, состояние данного объекта `COleCurrency` является недопустимым.  
  
 Если `COleCurrency` операнд является недопустимым, состояние данного объекта `COleCurrency` является недопустимым.  
  
 Дополнительные сведения о значениях состояния допустимым, недопустимым и null см. в разделе [m_status](#m_status) переменной-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]  
  
##  <a name="operator_stream"></a>  COleCurrency::operator &lt; &lt;, &gt;&gt;  
 Поддерживает диагностики создания дампа и хранение в архив.  
  
```  
friend CDumpContext& operator<<(
    CDumpContext& dc,  
    COleCurrency curSrc);
 
friend CArchive& operator<<(
    CArchive& ar,  
    COleCurrency curSrc);
 
friend CArchive& operator>>(
    CArchive& ar,  
    COleCurrency& curSrc);
```  
  
### <a name="remarks"></a>Примечания  
 Извлечение ( **>>**) оператор поддерживает загрузку из архива.  
  
##  <a name="operator_currency"></a>  COleCurrency::operator валюты  
 Возвращает `CURRENCY` структуры, значение которого копируется из этого `COleCurrency` объекта.  
  
```  
operator CURRENCY() const; 
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="parsecurrency"></a>  COleCurrency::ParseCurrency  
 Вызовите эту функцию-член для разбора строки для чтения значения валюты.  
  
```  
BOOL ParseCurrency(
    LPCTSTR lpszCurrency,  
    DWORD dwFlags = 0,  
    LCID lcid = LANG_USER_DEFAULT);
 
throw(CMemoryException*); 
throw(COleException*);
```  
  
### <a name="parameters"></a>Параметры  
 *lpszCurrency*  
 Указатель на заканчивающуюся нулем строку, который анализируется.  
  
 *dwFlags*  
 Указывает флаги для локали, возможно следующего флага:  
  
- LOCALE_NOUSEROVERRIDE использовать параметры языкового стандарта системы по умолчанию, а не пользовательские параметры пользователя.  
  
 *lcid*  
 Указывает идентификатор языкового стандарта для использования для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если строка была успешно преобразована в виде денежного значения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Она использует местный язык спецификации (идентификаторы языковых стандартов) для значения нечисловые знаки в исходной строке.  
  
 Описание значений Идентификаторов языкового стандарта, см. в разделе [поддержка нескольких языков](/previous-versions/windows/desktop/automat/supporting-multiple-national-languages).  
  
 Если строка успешно преобразован в валюту, значение, значение этого `COleCurrency` объекта имеет значение этого значения и его статус на допустимый.  
  
 Если строка не могут быть преобразованы в виде денежного значения, или если была численного переполнения, состояние данного объекта `COleCurrency` объекта является недопустимым.  
  
 Если строковое преобразование завершилось неудачей из-за ошибки выделения памяти, эта функция создает [CMemoryException](../../mfc/reference/cmemoryexception-class.md). В любом другом состоянии ошибки, эта функция создает [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]  
  
##  <a name="colecurrency_relational_operators"></a>  Операторы отношения COleCurrency  
 Сравнить два значения валюты и возвращать ненулевое значение, если условие равно true; в противном случае 0.  
  
```  
BOOL operator==(const COleCurrency& cur) const;  
BOOL operator!=(const COleCurrency& cur) const;  
BOOL operator<(const COleCurrency& cur) const;  
BOOL operator>(const COleCurrency& cur) const;  
BOOL operator<=(const COleCurrency& cur) const;  
BOOL operator>=(const COleCurrency& cur) const;  
```  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Возвращаемое значение упорядочивания операций ( **<**, **\< =**, **>**, **>=**) не определено, если состояние один из операндов равен null или недопустим. Операторы равенства ( `==`, `!=`) рассмотрите возможность состояние операндов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]  
  
##  <a name="setcurrency"></a>  COleCurrency::SetCurrency  
 Вызов этой функции-члена для задания единиц и дробной части `COleCurrency` объекта.  
  
```  
void SetCurrency(
    long nUnits,  
    long nFractionalUnits);
```  
  
### <a name="parameters"></a>Параметры  
 *nUnits*, *nFractionalUnits*  
 Укажите единицы и дробная часть значения (в 1/десятках тысяч) копируются в это `COleCurrency` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если абсолютное значение дробной части больше 10 000, соответствующих настроек единиц, как показано в третьем из следующих примеров.  
  
 Обратите внимание на то, что единицы и дробной части задаются значения со знаком длинное. Четвертая из приведенных ниже примерах показано, что произойдет, если параметры имеют различные знаки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]  
  
##  <a name="setstatus"></a>  COleCurrency::SetStatus  
 Эта функция-член для задания состояния (действия), это вызвать `COleCurrency` объекта.  
  
```  
void SetStatus(CurrencyStatus  status  );
```  
  
### <a name="parameters"></a>Параметры  
 *status*  
 Новое состояние для данного `COleCurrency` объекта.  
  
### <a name="remarks"></a>Примечания  
 *Состояние* значение параметра определяется `CurrencyStatus` перечислимый тип, который определен в `COleCurrency` класса.  
  
```  
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };  
```  
  
 Краткое описание этих значений состояния см. в следующем списке:  
  
- `COleCurrency::valid` Указывает, что этот `COleCurrency` объект является допустимым.  
  
- `COleCurrency::invalid` Указывает, что этот `COleCurrency` объекта является недопустимым; то есть его значение может быть неправильным.  
  
- `COleCurrency::null` Указывает, что этот `COleCurrency` объект имеет значение null, то есть, что значение не указано для этого объекта. (Это «null» в смысле «предложений having без значения,» в отличие от C++ NULL базы данных.)  
  
> [!CAUTION]
>  Эта функция служит для сложных ситуациях программирования. Эта функция не изменяет данные в этом объекте. Чаще всего он будет использоваться для задания состояния null или недопустимый. Обратите внимание, что оператор присваивания ( [оператор =](#operator_eq)) и [SetCurrency](#setcurrency) присвоить состояние объекта, в зависимости от исходного значения.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleVariant](../../mfc/reference/colevariant-class.md)
