---
title: "Класс COleCurrency | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8d20b0f61fc7773899e671bec5b252ef2af1abf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
|[COleCurrency::Format](#format)|Создает строковое представление `COleCurrency` объекта.|  
|[COleCurrency::GetStatus](#getstatus)|Возвращает состояние (действия) это `COleCurrency` объекта.|  
|[COleCurrency::ParseCurrency](#parsecurrency)|Считывает **валюты** значение из строки и задает значение `COleCurrency`.|  
|[COleCurrency::SetCurrency](#setcurrency)|Задает значение этого `COleCurrency` объекта.|  
|[COleCurrency::SetStatus](#setstatus)|Задает состояние (действия) для этого `COleCurrency` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[оператор =](#operator_eq)|Копирует `COleCurrency` значение.|  
|[оператор +, -](#operator_plus_minus)|Добавляет, вычитает и изменяет знак `COleCurrency` значения.|  
|[оператор +=-=](#operator_plus_minus_eq)|Добавляет и вычитает `COleCurrency` значение из этого `COleCurrency` объекта.|  
|[оператор * /](#operator_star)|Масштабирует `COleCurrency` значение целое значение.|  
|[оператор * = и =](#operator_star_div_eq)|Масштабирует это `COleCurrency` значение целое значение.|  
|[оператор <<](#operator_stream)|Выходные данные `COleCurrency` значение `CArchive` или `CDumpContext`.|  
|[оператор >>](#operator_stream)|Входные данные `COleCurrency` объекта из `CArchive`.|  
|[оператор валюты](#operator_currency)|Преобразует `COleCurrency` значение в **валюты**.|  
|[оператор ==, <, < = и т. д.](#colecurrency_relational_operators)|Сравнивает два `COleCurrency` значения.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleCurrency::m_cur](#m_cur)|Содержит базовый **валюты** для этого `COleCurrency` объекта.|  
|[COleCurrency::m_status](#m_status)|Содержит состояние данного объекта `COleCurrency` объекта.|  
  
## <a name="remarks"></a>Примечания  
 **COleCurrency** не имеет базового класса.  
  
 **ВАЛЮТА** реализуется в виде 8 байт, дополнительном целочисленное значение, умноженное на 10 000. Это позволяет получить число с фиксированной запятой с 15 разрядами слева от десятичной запятой и 4 разрядами справа от нее. **Валюты** тип данных чрезвычайно полезна для денежных расчетов или для любого вычисления с фиксированной запятой, когда важна точность. Это один из возможных типов для `VARIANT` тип данных OLE-автоматизации.  
  
 **COleCurrency** также реализует некоторые основные арифметические операции, для этого типа с фиксированной запятой. Поддерживаемые операции были выбраны для управления ошибками округления, происходящих во время вычислений с фиксированной запятой.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `COleCurrency`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
##  <a name="colecurrency"></a>COleCurrency::COleCurrency  
 Создает **COleCurrency** объекта.  
  
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
 `cySrc`  
 Объект **валюты** значения, которое копируется в новый **COleCurrency** объекта.  
  
 `curSrc`  
 Существующий **COleCurrency** скопировать в новый объект **COleCurrency** объекта.  
  
 *varSrc*  
 Существующий **VARIANT** структура данных (возможно `COleVariant` объекта) должно быть преобразовано в значение валюты ( `VT_CY`) и скопировать в новый **COleCurrency** объекта.  
  
 `nUnits`, `nFractionalUnits`  
 Указывает единицы и дробная часть значения (в 1/10, 000's), чтобы скопировать в новый **COleCurrency** объекта.  
  
### <a name="remarks"></a>Примечания  
 Все эти конструкторы создавать новые **COleCurrency** объекты, инициализированные до указанного значения. Следует краткое описание каждого из этих конструкторов. Если не указано иное состояние нового **COleCurrency** элемента имеет значение на допустимое.  
  
- Конструкции COleCurrency() **COleCurrency** объект инициализируется значением 0 (ноль).  
  
- COleCurrency (`cySrc`) создает **COleCurrency** объекта из [валюты](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) значение.  
  
- COleCurrency (`curSrc`) создает **COleCurrency** объекта из существующего **COleCurrency** объекта. Новый объект имеет такое же состояние, что и исходный объект.  
  
- COleCurrency (`varSrc`) создает **COleCurrency** объекта. Пытается преобразовать [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) структуры или `COleVariant` объект валюты ( `VT_CY`) значение. Если преобразование прошло успешно, преобразованное значение копируется в новый **COleCurrency** объекта. Если это не так, значение **COleCurrency** , присваивается значение ноль (0) и его состояние недопустимой.  
  
- `COleCurrency(`nUnits`, `nFractionalUnits) создает **COleCurrency** объекта из указанных числовых компонентов. Если абсолютным значением дробной части больше 10 000, то соответствующие выполняется корректировка подразделениям. Обратите внимание, что единицы и дробной части задаются с помощью подписи длинные значения.  
  
 Дополнительные сведения см. в разделе [валюты](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) и [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) записи в Windows SDK.  
  
### <a name="example"></a>Пример  
 В следующих примерах показано влияние конструкторы параметра нулевого и два параметра:  
  
 [!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]  
  
##  <a name="format"></a>COleCurrency::Format  
 Вызовите эту функцию-член для создания отформатированное представление значения валюты.  
  
```  
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const; 
```  
  
### <a name="parameters"></a>Параметры  
 `dwFlags`  
 Указывает флаги для региональных параметров. Только следующие флаг действителен для валюты:  
  
- **LOCALE_NOUSEROVERRIDE** использовать параметры языкового стандарта системы по умолчанию, а не пользовательских параметров.  
  
 `lcid`  
 Указывает код языка, используют для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `CString` , содержащий значение в формате валюты.  
  
### <a name="remarks"></a>Примечания  
 Он форматирует значение с помощью спецификации местных языках (идентификаторы языковых стандартов). Символ валюты не включается в возвращаемом значении. Если это состояние **COleCurrency** объект имеет значение null, возвращается пустая строка. Если состояние является недопустимым, возвращаемая строка определяется строковый ресурс **IDS_INVALID_CURRENCY**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]  
  
##  <a name="getstatus"></a>COleCurrency::GetStatus  
 Вызовите эту функцию-член для получения состояния (действия) заданного **COleCurrency** объекта.  
  
```  
CurrencyStatus GetStatus() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает состояние данного объекта **COleCurrency** значение.  
  
### <a name="remarks"></a>Примечания  
 Возвращаемое значение определяется `CurrencyStatus` перечисляемый тип, в котором определен **COleCurrency** класса.  
  
```  
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };  
```  
  
 Краткое описание этих значений состояния см. следующий список:  
  
- **COleCurrency::valid** указывает этим **COleCurrency** объект является допустимым.  
  
- **COleCurrency::invalid** указывает этим **COleCurrency** объекта является недопустимым; то есть его значение может быть неправильным.  
  
- **COleCurrency::null** указывает этим **COleCurrency** объект имеет значение null, то есть, что значение не были указаны для данного объекта. (Это «null» в смысле базы данных «предложений having без значения,» в отличие от C++ **NULL**.)  
  
 Состояние **COleCurrency** недопустимый объект в следующих случаях:  
  
-   Если его значение установлено из **VARIANT** или `COleVariant` значение, которое не удалось преобразовать значение валюты.  
  
-   Если этот объект в результате переполнения или потери значимости во время операции присваивания арифметические, например `+=` или  **\* =** .  
  
-   Если к этому объекту было присвоено недопустимое значение.  
  
-   Если состояние этого объекта явно установленного на недопустимый с помощью [SetStatus](#setstatus).  
  
 Дополнительные сведения об операциях, которые может присвоить состояние недопустимый см. в разделе следующие функции-члены:  
  
- [COleCurrency](#colecurrency)  
  
- [оператор =](#operator_eq)  
  
- [оператор + -](#operator_plus_minus)  
  
- [оператор += и-=](#operator_plus_minus_eq)  
  
- [оператор * /](#operator_star)  
  
- [оператор * = и / =](#operator_star_div_eq)  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]  
  
##  <a name="m_cur"></a>COleCurrency::m_cur  
 Базовый [валюты](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) структуры для этого **COleCurrency** объекта.  
  
### <a name="remarks"></a>Примечания  
  
> [!CAUTION]
>  Изменение значения в **валюты** структуры обращаются указатель, возвращаемый этой функцией изменит значение этой **COleCurrency** объекта. Это не приводит к изменению состояния этого **COleCurrency** объекта.  
  
 Дополнительные сведения см. в разделе [валюты](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) входа в Windows SDK.  
  
##  <a name="m_status"></a>COleCurrency::m_status  
 Тип этого элемента данных является перечисляемым типом `CurrencyStatus`, которая определена в **COleCurrency** класса.  
  
```  
enum CurrencyStatus{  
    valid = 0,  
    invalid = 1,  
    null = 2,  
};  
```  
  
### <a name="remarks"></a>Примечания  
 Краткое описание этих значений состояния см. следующий список:  
  
- **COleCurrency::valid** указывает этим **COleCurrency** объект является допустимым.  
  
- **COleCurrency::invalid** указывает этим **COleCurrency** объекта является недопустимым; то есть его значение может быть неправильным.  
  
- **COleCurrency::null** указывает этим **COleCurrency** объект имеет значение null, то есть, что значение не были указаны для данного объекта. (Это «null» в смысле базы данных «предложений having без значения,» в отличие от C++ **NULL**.)  
  
 Состояние **COleCurrency** недопустимый объект в следующих случаях:  
  
-   Если его значение установлено из **VARIANT** или `COleVariant` значение, которое не удалось преобразовать значение валюты.  
  
-   Если этот объект в результате переполнения или потери значимости во время операции присваивания арифметические, например `+=` или  **\* =** .  
  
-   Если к этому объекту было присвоено недопустимое значение.  
  
-   Если состояние этого объекта явно установленного на недопустимый с помощью [SetStatus](#setstatus).  
  
 Дополнительные сведения об операциях, которые может присвоить состояние недопустимый см. в разделе следующие функции-члены:  
  
- [COleCurrency](#colecurrency)  
  
- [оператор =](#operator_eq)  
  
- [оператор +, -](#operator_plus_minus)  
  
- [оператор +=-=](#operator_plus_minus_eq)  
  
- [оператор * /](#operator_star)  
  
- [оператор * = и =](#operator_star_div_eq)  
  
    > [!CAUTION]
    >  Этот член данных — для сложных ситуациях программирования. Следует использовать подставляемые функции-члены [GetStatus](#getstatus) и [SetStatus](#setstatus). В разделе `SetStatus` дополнительные предупреждения, касающиеся явного задания этого элемента данных.  
  
##  <a name="operator_eq"></a>COleCurrency::operator =  
 Эти перегруженных операторах присваивания копирования исходного значения валюты в это **COleCurrency** объекта.  
  
```  
const COleCurrency& operator=(CURRENCY cySrc);  
const COleCurrency& operator=(const COleCurrency& curSrc);  
  const COleCurrency& operator=(const VARIANT& varSrc);
```  
  
### <a name="remarks"></a>Примечания  
 Краткое описание каждого оператора выглядит следующим образом:  
  
- **оператор = (** `cySrc` **)** `CURRENCY` значение будет скопировано в **COleCurrency** объекта и его состояние имеет значение на допустимое.  
  
- **оператор = (** `curSrc` **)** значение и состояние операнда существующего **COleCurrency** объекта будут скопированы в это **COleCurrency** объект.  
  
- **оператор = (** *varSrc* **)** Если преобразование `VARIANT` значение (или [COleVariant](../../mfc/reference/colevariant-class.md) объект) для валюты ( `VT_CY`) — успешно, преобразованное значение копируется в этот **COleCurrency** объекта и его состояние имеет значение на допустимое. Если преобразование не прошла успешно, значение **COleCurrency** , присваивается значение 0 и его статус на недопустимый.  
  
 Дополнительные сведения см. в разделе [валюты](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) и [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) записи в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]  
  
##  <a name="operator_plus_minus"></a>COleCurrency::operator +, -  
 Эти операторы позволяют сложения и вычитания двух **COleCurrency** значения, а друг от друга и изменение знак **COleCurrency** значение.  
  
```  
COleCurrency operator+(const COleCurrency& cur) const;  
COleCurrency operator-(const COleCurrency& cur) const;  
COleCurrency operator-() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Если любой из операндов равен null, итоговое состояние **COleCurrency** имеет значение null.  
  
 Если арифметическое переполнение при выполнении операции, итоговый **COleCurrency** недопустимое значение.  
  
 Если операнд является недопустимым, а другой является не null, итоговое состояние **COleCurrency** недопустимое значение.  
  
 Дополнительные сведения о значениях состояния недопустимый, допустимый и null. в разделе [m_status](#m_status) переменной-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]  
  
##  <a name="operator_plus_minus_eq"></a>COleCurrency::operator +=-=  
 Позволяют сложения и вычитания **COleCurrency** значение в и из этого **COleCurrency** объекта.  
  
```  
const COleCurrency& operator+=(const COleCurrency& cur);  
const COleCurrency& operator-=(const COleCurrency& cur);
```  
  
### <a name="remarks"></a>Примечания  
 Если любой из операндов имеет значение null, это состояние **COleCurrency** объекта установлено в значение null.  
  
 Если арифметическое переполнение при выполнении операции, это состояние **COleCurrency** объекта установлено недопустимой.  
  
 Если один из операндов является недопустимым, и другой не равно null, это состояние **COleCurrency** объекта установлено недопустимой.  
  
 Дополнительные сведения о значениях состояния недопустимый, допустимый и null. в разделе [m_status](#m_status) переменной-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]  
  
##  <a name="operator_star"></a>COleCurrency::operator * и /  
 Позволяют масштабировать **COleCurrency** значение с целочисленным значением.  
  
```  
COleCurrency operator*(long nOperand) const;  
COleCurrency operator/(long nOperand) const;  
```  
  
### <a name="remarks"></a>Примечания  
 Если **COleCurrency** операнд имеет значение null, итоговое состояние **COleCurrency** имеет значение null.  
  
 При переполнении арифметической операции или потеря значимости, итоговое состояние **COleCurrency** недопустимое значение.  
  
 Если **COleCurrency** операнд является недопустимым, итоговое состояние **COleCurrency** недопустимое значение.  
  
 Дополнительные сведения о значениях состояния недопустимый, допустимый и null. в разделе [m_status](#m_status) переменной-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]  
  
##  <a name="operator_star_div_eq"></a>COleCurrency::operator * = и =  
 Позволяют масштаба **COleCurrency** значение с целочисленным значением.  
  
```  
const COleCurrency& operator*=(long nOperand);  
const COleCurrency& operator/=(long nOperand);
```  
  
### <a name="remarks"></a>Примечания  
 Если **COleCurrency** операнд имеет значение null, это состояние **COleCurrency** объекта установлено значение null.  
  
 Если арифметическое переполнение при выполнении операции, это состояние **COleCurrency** объекта установлено недопустимой.  
  
 Если **COleCurrency** операнд является недопустимым, это состояние **COleCurrency** объекта установлено недопустимой.  
  
 Дополнительные сведения о значениях состояния недопустимый, допустимый и null. в разделе [m_status](#m_status) переменной-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]  
  
##  <a name="operator_stream"></a>COleCurrency::operator &lt; &lt;,&gt;&gt;  
 Поддерживает формирование дампа диагностики и хранение в архив.  
  
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
 Извлечение (  **>>** ) оператор поддерживает загрузку из архива.  
  
##  <a name="operator_currency"></a>COleCurrency::operator ВАЛЮТ  
 Возвращает `CURRENCY` , значение которого копируется из этой структуры **COleCurrency** объекта.  
  
```  
operator CURRENCY() const; 
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="parsecurrency"></a>COleCurrency::ParseCurrency  
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
 Указатель на завершающуюся значением null строке, которая является для синтаксического анализа.  
  
 `dwFlags`  
 Указывает флаги для локали, возможно следующих флага:  
  
- **LOCALE_NOUSEROVERRIDE** использовать параметры языкового стандарта системы по умолчанию, а не пользовательских параметров.  
  
 `lcid`  
 Указывает код языка, используют для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если строка был успешно преобразован в виде денежного значения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Он использует местный язык спецификации (идентификаторы языковых стандартов) для значения нечисловых знаков в строке исходного.  
  
 Описание значений Идентификаторов языкового стандарта, в разделе [поддержки нескольких языков](http://msdn.microsoft.com/en-us/47dc5add-232c-4268-b977-43e12da81ede).  
  
 Если строка был успешно преобразован в валюту значение, значение этого аргумента **COleCurrency** , присваивается значение этого значения и его статус на допустимое.  
  
 Если не удалось преобразовать строку в виде денежного значения, или если была численного переполнения состояние данного объекта **COleCurrency** недопустимый объект.  
  
 Если не удалось выполнить преобразование строк из-за ошибки выделения памяти, эта функция вызывает [CMemoryException](../../mfc/reference/cmemoryexception-class.md). В любом другом состоянии ошибки, эта функция вызывает [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]  
  
##  <a name="colecurrency_relational_operators"></a>Реляционные операторы COleCurrency  
 Сравнить два значения валюты и возвращает ненулевое значение, если условие имеет значение true; в противном случае — 0.  
  
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
>  Возвращаемое значение для упорядочивания операций (  **<** ,  **\< =** ,  **>** ,  **>=** ) не определено, если состояние одного из операндов имеет значение null или недопустимый. Операторы равенства ( `==`, `!=`) рассмотрите возможность состояние операндов.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]  
  
##  <a name="setcurrency"></a>COleCurrency::SetCurrency  
 Вызовите эту функцию-член для задания единиц измерения и дробную часть **COleCurrency** объекта.  
  
```  
void SetCurrency(
    long nUnits,  
    long nFractionalUnits);
```  
  
### <a name="parameters"></a>Параметры  
 `nUnits`, `nFractionalUnits`  
 Указывает единицы и дробная часть значения (в 1/10, 000's), необходимо скопировать в это **COleCurrency** объекта.  
  
### <a name="remarks"></a>Примечания  
 Если абсолютным значением дробной части больше 10 000, соответствующие коррекция выполняется единицы измерения, как показано в третьем из следующих примеров.  
  
 Обратите внимание, что единицы и дробной части задаются с помощью подписи длинные значения. Четвертый следующих примерах показано, что произойдет, если параметры имеют различные знаки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]  
  
##  <a name="setstatus"></a>COleCurrency::SetStatus  
 Вызовите эту функцию-член для задания состояния (действия) это **COleCurrency** объекта.  
  
```  
void SetStatus(CurrencyStatus  status  );
```  
  
### <a name="parameters"></a>Параметры  
 *status*  
 Новый статус **COleCurrency** объекта.  
  
### <a name="remarks"></a>Примечания  
 *Состояние* значение параметра определяется `CurrencyStatus` перечисляемый тип, который определен в **COleCurrency** класса.  
  
```  
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };  
```  
  
 Краткое описание этих значений состояния см. следующий список:  
  
- **COleCurrency::valid** указывает этим **COleCurrency** объект является допустимым.  
  
- **COleCurrency::invalid** указывает этим **COleCurrency** объекта является недопустимым; то есть его значение может быть неправильным.  
  
- **COleCurrency::null** указывает этим **COleCurrency** объект имеет значение null, то есть, что значение не были указаны для данного объекта. (Это «null» в смысле базы данных «предложений having без значения,» в отличие от C++ **NULL**.)  
  
    > [!CAUTION]
    >  Эта функция предназначена для сложных ситуациях программирования. Эта функция не изменяет данные в этом объекте. Чаще всего он будет использоваться для задания состояния в значение null или является недопустимым. Обратите внимание, что оператор присваивания ( [оператор =](#operator_eq)) и [SetCurrency](#setcurrency) присвоить состояние объекта, в зависимости от исходного значения.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleVariant](../../mfc/reference/colevariant-class.md)
