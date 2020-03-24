---
title: Класс COleCurrency
ms.date: 08/29/2019
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
ms.openlocfilehash: 1e32d75599f51ba277180341df60762a02a82fe5
ms.sourcegitcommit: eff68e4e82be292a5664616b16a526df3e9d1cda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80150933"
---
# <a name="colecurrency-class"></a>Класс COleCurrency

Инкапсулирует тип данных `CURRENCY` автоматизации OLE.

## <a name="syntax"></a>Синтаксис

```
class COleCurrency
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[COleCurrency:: COleCurrency](#colecurrency)|Формирует объект `COleCurrency`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[COleCurrency:: Format](#format)|Формирует форматированное строковое представление объекта `COleCurrency`.|
|[COleCurrency::/Status](#getstatus)|Возвращает состояние (допустимость) данного объекта `COleCurrency`.|
|[COleCurrency::P Арсекурренци](#parsecurrency)|Считывает значение валюты из строки и задает значение `COleCurrency`.|
|[COleCurrency:: Сеткурренци](#setcurrency)|Задает значение данного объекта `COleCurrency`.|
|[COleCurrency:: SetStatus](#setstatus)|Задает состояние (допустимость) для данного объекта `COleCurrency`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[Оператор =](#operator_eq)|Копирует `COleCurrency` значение.|
|[operator +,-](#operator_plus_minus)|Добавляет, вычитает и изменяет знак `COleCurrency` значений.|
|[operator + =,-=](#operator_plus_minus_eq)|Добавляет и вычитает значение `COleCurrency` из этого `COleCurrency` объекта.|
|[Оператор */](#operator_star)|Масштабирует `COleCurrency` значение по целому значению.|
|[operator * =,/=](#operator_star_div_eq)|Масштабирует это `COleCurrency` значение с помощью целочисленного значения.|
|[< оператора <](#operator_stream)|Выводит `COleCurrency` значение для `CArchive` или `CDumpContext`.|
|[> оператора >](#operator_stream)|Вводит `COleCurrency` объект из `CArchive`.|
|[Валюта оператора](#operator_currency)|Преобразует значение `COleCurrency` в ДЕНЕЖную ЕДИНИЦу.|
|[operator = =, <, < = и т. д.](#colecurrency_relational_operators)|Сравнивает два значения `COleCurrency`.|

### <a name="public-data-members"></a>Открытые элементы данных

|Имя|Description|
|----------|-----------------|
|[COleCurrency:: m_cur](#m_cur)|Содержит базовую ВАЛЮТу для данного объекта `COleCurrency`.|
|[COleCurrency:: m_status](#m_status)|Содержит состояние данного объекта `COleCurrency`.|

## <a name="remarks"></a>Remarks

`COleCurrency` не имеет базового класса.

Валюта реализуется как 8-байтовое целочисленное значение, которое масштабируется по 10 000. Это позволяет получить число с фиксированной запятой с 15 разрядами слева от десятичной запятой и 4 разрядами справа от нее. Тип данных CURRENCY чрезвычайно удобен для вычислений, связанных с деньгами, или для любых вычислений с фиксированной запятой, где важна точность. Это один из возможных типов `VARIANT` типа данных OLE Automation.

`COleCurrency` также реализует некоторые базовые арифметические операции для этого типа с фиксированной запятой. Для управления ошибками округления, происходящих во время вычислений с фиксированной запятой, выбраны поддерживаемые операции.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`COleCurrency`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

##  <a name="colecurrencycolecurrency"></a><a name="colecurrency"></a>COleCurrency:: COleCurrency

Формирует объект `COleCurrency`.

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

*цисрк*<br/>
Значение валюты, которое должно быть скопировано в новый объект `COleCurrency`.

*курсрк*<br/>
Существующий объект `COleCurrency` для копирования в новый объект `COleCurrency`.

*варсрк*<br/>
Существующая структура данных `VARIANT` (возможно, объект `COleVariant`) будет преобразована в значение валюты (VT_CY) и скопирована в новый объект `COleCurrency`.

*нунитс*, *нфрактионалунитс* указывает единицы и дробную часть значения, которое будет скопировано в новый объект `COleCurrency` (в 1/10000).

### <a name="remarks"></a>Remarks

Все эти конструкторы создают новые `COleCurrency` объекты, инициализированные с указанным значением. Ниже приведено краткое описание каждого из этих конструкторов. Если не указано иное, состояние нового элемента `COleCurrency` устанавливается как допустимое.

- COleCurrency () конструирует объект `COleCurrency`, инициализированный значением 0 (ноль).

- COleCurrency (`cySrc`) конструирует объект `COleCurrency` из значения [валюты](/windows/win32/api/wtypes/ns-wtypes-cy~r1) .

- COleCurrency (`curSrc`) конструирует объект `COleCurrency` из существующего объекта `COleCurrency`. Новый объект имеет то же состояние, что и исходный объект.

- COleCurrency (`varSrc`) конструирует объект `COleCurrency`. Пытается преобразовать структуру [Variant](/windows/win32/api/oaidl/ns-oaidl-variant) или `COleVariant` объект в значение валюты (VT_CY). Если это преобразование выполнено успешно, преобразованное значение копируется в новый объект `COleCurrency`. Если это не так, значение объекта `COleCurrency` задается равным нулю (0), а его состояние — "Недопустимый".

- COleCurrency (`nUnits`, `nFractionalUnits`) конструирует объект `COleCurrency` из указанных числовых компонентов. Если абсолютное значение дробной части больше 10 000, в единицы измерения вносится соответствующая корректировка. Обратите внимание, что единицы и дробная часть указываются с помощью длинных значений со знаком.

Дополнительные сведения см. в разделе [Валюта](/windows/win32/api/wtypes/ns-wtypes-cy~r1) и [варианты](/windows/win32/api/oaidl/ns-oaidl-variant) в Windows SDK.

### <a name="example"></a>Пример

В следующих примерах показаны последствия использования параметров и конструкторов с нулевым параметром:

[!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]

##  <a name="colecurrencyformat"></a><a name="format"></a>COleCurrency:: Format

Вызовите эту функцию-член, чтобы создать форматированное представление значения валюты.

```
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const;
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Указывает флаги для параметров языкового стандарта. Только следующий флаг относится к валюте:

- LOCALE_NOUSEROVERRIDE использовать системные параметры по умолчанию, а не пользовательские параметры пользователя.

*lcid*<br/>
Указывает код локали, используемый для преобразования.

### <a name="return-value"></a>Возвращаемое значение

`CString`, содержащая отформатированное значение валюты.

### <a name="remarks"></a>Remarks

Он форматирует значение, используя спецификации локального языка (идентификаторы локали). Символ валюты не включается в возвращаемое значение. Если состояние этого `COleCurrency` объекта равно null, то возвращаемое значение является пустой строкой. Если состояние является недопустимым, возвращаемая строка указывается строковым ресурсом IDS_INVALID_CURRENCY.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]

##  <a name="colecurrencygetstatus"></a><a name="getstatus"></a>COleCurrency::/Status

Вызовите эту функцию-член, чтобы получить состояние (действительность) заданного `COleCurrency` объекта.

```
CurrencyStatus GetStatus() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает состояние этого `COleCurrency` значения.

### <a name="remarks"></a>Remarks

Возвращаемое значение определяется `CurrencyStatus` перечислимым типом, определенным в классе `COleCurrency`.

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

Краткое описание этих значений состояния см. в следующем списке:

  - `COleCurrency::valid` указывает, что этот `COleCurrency` объект является допустимым.

  - `COleCurrency::invalid` указывает, что этот `COleCurrency` объект является недопустимым; то есть его значение может быть неправильным.

  - `COleCurrency::null` указывает, что этот `COleCurrency` объект имеет значение null, то есть для этого объекта не было предоставлено значение. (Значение NULL в базе данных имеет значение «не имеет значения», а в отличие от C++ значения NULL).

Состояние объекта `COleCurrency` недопустимо в следующих случаях:

- Если его значение задано из варианта или `COleVariant` значения, которое не может быть преобразовано в денежное значение.

- Если в этом объекте произошло переполнение или потеря точности во время операции арифметического присваивания, например `+=` или **\*=** .

- Если этому объекту было присвоено недопустимое значение.

- Значение, если состояние этого объекта было явно задано как недопустимое с помощью [SetStatus](#setstatus).

Дополнительные сведения об операциях, которые могут установить состояние "недопустимо", см. в следующих функциях элементов:

- [COleCurrency](#colecurrency)

- [Оператор =](#operator_eq)

- [operator +-](#operator_plus_minus)

- [operator + = и-=](#operator_plus_minus_eq)

- [Оператор */](#operator_star)

- [operator * = и/=](#operator_star_div_eq)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]

##  <a name="colecurrencym_cur"></a><a name="m_cur"></a>COleCurrency:: m_cur

Базовая структура [валюты](/windows/win32/api/wtypes/ns-wtypes-cy~r1) для данного объекта `COleCurrency`.

### <a name="remarks"></a>Remarks

> [!CAUTION]
>  Изменение значения в структуре `CURRENCY`, к которой обращается указатель, возвращаемой этой функцией, приведет к изменению значения этого `COleCurrency` объекта. Он не изменяет состояние этого объекта `COleCurrency`.

Дополнительные сведения см. в записи [валюты](/windows/win32/api/wtypes/ns-wtypes-cy~r1) в Windows SDK.

##  <a name="colecurrencym_status"></a><a name="m_status"></a>COleCurrency:: m_status

Тип этого элемента данных — перечислимый тип `CurrencyStatus`, который определен в классе `COleCurrency`.

```
enum CurrencyStatus{
    valid = 0,
    invalid = 1,
    null = 2,
};
```

### <a name="remarks"></a>Remarks

Краткое описание этих значений состояния см. в следующем списке:

- `COleCurrency::valid` указывает, что этот `COleCurrency` объект является допустимым.

- `COleCurrency::invalid` указывает, что этот `COleCurrency` объект является недопустимым; то есть его значение может быть неправильным.

- `COleCurrency::null` указывает, что этот `COleCurrency` объект имеет значение null, то есть для этого объекта не было предоставлено значение. (Значение NULL в базе данных имеет значение «не имеет значения», а в отличие от C++ значения NULL).

Состояние объекта `COleCurrency` недопустимо в следующих случаях:

- Если его значение задано из варианта или `COleVariant` значения, которое не может быть преобразовано в денежное значение.

- Если в этом объекте произошло переполнение или потеря точности во время операции арифметического присваивания, например `+=` или **\*=** .

- Если этому объекту было присвоено недопустимое значение.

- Значение, если состояние этого объекта было явно задано как недопустимое с помощью [SetStatus](#setstatus).

Дополнительные сведения об операциях, которые могут установить состояние "недопустимо", см. в следующих функциях элементов:

- [COleCurrency](#colecurrency)

- [Оператор =](#operator_eq)

- [operator +,-](#operator_plus_minus)

- [operator + =,-=](#operator_plus_minus_eq)

- [Оператор */](#operator_star)

- [operator * =,/=](#operator_star_div_eq)

> [!CAUTION]
>  Этот элемент данных предназначен для более сложных сценариев программирования. Следует использовать встроенные функции элементов с параметром " [Status](#getstatus) " и [SetStatus](#setstatus). Дополнительные предостережения по явному заданию этого элемента данных см. в разделе `SetStatus`.

##  <a name="colecurrencyoperator-"></a><a name="operator_eq"></a>COleCurrency:: operator =

Эти перегруженные операторы присваивания копируют значение исходной валюты в этот объект `COleCurrency`.

```
const COleCurrency& operator=(CURRENCY cySrc);
const COleCurrency& operator=(const COleCurrency& curSrc);
const COleCurrency& operator=(const VARIANT& varSrc);
```

### <a name="remarks"></a>Remarks

Краткое описание каждого оператора приведено ниже.

- **operator = (** `cySrc` **)** Значение `CURRENCY` копируется в объект `COleCurrency`, а его состояние имеет значение Valid.

- **operator = (** `curSrc` **)** Значение и состояние операнда — существующий объект `COleCurrency` копируется в этот `COleCurrency` объект.

- **operator = (** *варсрк* **)** Если преобразование `VARIANT` значения (или объекта [COleVariant](../../mfc/reference/colevariant-class.md) ) в валюту (`VT_CY`) выполнено успешно, преобразованное значение копируется в этот `COleCurrency` объект и его состояние устанавливается в значение Valid. Если преобразование завершилось неудачно, значение объекта `COleCurrency` задается равным 0, а его состояние — "недопустимо".

Дополнительные сведения см. в разделе [Валюта](/windows/win32/api/wtypes/ns-wtypes-cy~r1) и [варианты](/windows/win32/api/oaidl/ns-oaidl-variant) в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]

##  <a name="colecurrencyoperator---"></a><a name="operator_plus_minus"></a>COleCurrency:: operator +,-

Эти операторы позволяют добавлять и вычитать два `COleCurrency` значений между ними и для изменения знака значения `COleCurrency`.

```
COleCurrency operator+(const COleCurrency& cur) const;
COleCurrency operator-(const COleCurrency& cur) const;
COleCurrency operator-() const;
```

### <a name="remarks"></a>Remarks

Если любой из операндов имеет значение null, то состояние результирующего `COleCurrency` будет равно null.

Если арифметическая операция переполняется, результирующее `COleCurrency` значение недопустимо.

Если операнд является недопустимым и второй не равен null, состояние результирующего `COleCurrency`ного значения недопустимо.

Дополнительные сведения о допустимых, недопустимых и нулевых значениях состояния см. в разделе переменная члена [M_STATUS](#m_status) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]

##  <a name="colecurrencyoperator---"></a><a name="operator_plus_minus_eq"></a>COleCurrency:: operator + =,-=

Позволяет добавлять и вычитать значения `COleCurrency` в этом `COleCurrency` объекте.

```
const COleCurrency& operator+=(const COleCurrency& cur);
const COleCurrency& operator-=(const COleCurrency& cur);
```

### <a name="remarks"></a>Remarks

Если какой-либо из операндов имеет значение null, состояние этого `COleCurrency` объекта равно null.

Если арифметическая операция переполняется, состояние этого объекта `COleCurrency` задается как недопустимое.

Если один из операндов является недопустимым, а второй не равен null, то для этого `COleCurrency` объекта задается недопустимое состояние.

Дополнительные сведения о допустимых, недопустимых и нулевых значениях состояния см. в разделе переменная члена [M_STATUS](#m_status) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]

##  <a name="colecurrencyoperator--and-"></a><a name="operator_star"></a>COleCurrency:: operator \* и/

Позволяет масштабировать `COleCurrency` значение по целочисленному значению.

```
COleCurrency operator*(long nOperand) const;
COleCurrency operator/(long nOperand) const;
```

### <a name="remarks"></a>Remarks

Если `COleCurrency` операнд имеет значение null, состояние результирующего `COleCurrency` имеет значение null.

Если арифметическая операция переполняет или потеряна, состояние полученного `COleCurrency` недопустимо.

Если `COleCurrency` операнд является недопустимым, состояние полученного `COleCurrency`ного значения является недопустимым.

Дополнительные сведения о допустимых, недопустимых и нулевых значениях состояния см. в разделе переменная члена [M_STATUS](#m_status) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]

##  <a name="colecurrencyoperator--"></a><a name="operator_star_div_eq"></a>COleCurrency:: operator \*=,/=

Позволяет масштабировать это `COleCurrency` значение по целочисленному значению.

```
const COleCurrency& operator*=(long nOperand);
const COleCurrency& operator/=(long nOperand);
```

### <a name="remarks"></a>Remarks

Если `COleCurrency` операнд имеет значение null, состояние этого `COleCurrency` объекта задается равным null.

Если арифметическая операция переполняется, состояние этого объекта `COleCurrency` задается как недопустимое.

Если `COleCurrency` операнд является недопустимым, состояние этого `COleCurrency` объекта задается как недопустимое.

Дополнительные сведения о допустимых, недопустимых и нулевых значениях состояния см. в разделе переменная члена [M_STATUS](#m_status) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]

##  <a name="colecurrencyoperator-ltlt-gtgt"></a><a name="operator_stream"></a>COleCurrency:: operator &lt;&lt;, &gt;&gt;

Поддерживает дампы и хранение в архиве.

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

### <a name="remarks"></a>Remarks

Оператор извлечения ( **>>** ) поддерживает загрузку из архива.

##  <a name="colecurrencyoperator-currency"></a><a name="operator_currency"></a>COleCurrency:: оператор CURRENCY

Возвращает структуру `CURRENCY`, значение которой копируется из этого `COleCurrency` объекта.

```
operator CURRENCY() const;
```

### <a name="remarks"></a>Remarks

##  <a name="colecurrencyparsecurrency"></a><a name="parsecurrency"></a>COleCurrency::P Арсекурренци

Вызовите эту функцию-член, чтобы проанализировать строку для считывания значения валюты.

```
BOOL ParseCurrency(
    LPCTSTR lpszCurrency,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT);

throw(CMemoryException*);
throw(COleException*);
```

### <a name="parameters"></a>Параметры

*лпсзкурренци*<br/>
Указатель на строку, завершающуюся нулем, которая должна быть проанализирована.

*dwFlags*<br/>
Указывает флаги для параметров языкового стандарта, возможно, следующего флага:

- LOCALE_NOUSEROVERRIDE использовать системные параметры по умолчанию, а не пользовательские параметры пользователя.

*lcid*<br/>
Указывает код локали, используемый для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если строка была успешно преобразована в денежную единицу; в противном случае — 0.

### <a name="remarks"></a>Remarks

Он использует спецификации локальных языков (идентификаторов локали) для значения нецифровых символов в исходной строке.

Описание значений идентификатора локали см. в разделе [Поддержка нескольких языков](/previous-versions/windows/desktop/automat/supporting-multiple-national-languages).

Если строка была успешно преобразована в денежное значение, то этому объекту `COleCurrency` присваивается значение, а его состояние — Valid.

Если строка не может быть преобразована в денежное значение или произошло числовое переполнение, состояние этого `COleCurrency` объекта недопустимо.

Если преобразование строки завершилось ошибкой из-за ошибок выделения памяти, эта функция создает исключение [CMemoryException](../../mfc/reference/cmemoryexception-class.md). В любом другом состоянии ошибки эта функция создает исключение [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]

##  <a name="colecurrency-relational-operators"></a><a name="colecurrency_relational_operators"></a>Операторы отношения COleCurrency

Сравнение двух значений валют и возврат ненулевого значения, если условие истинно; в противном случае — 0.

```
BOOL operator==(const COleCurrency& cur) const;
BOOL operator!=(const COleCurrency& cur) const;
BOOL operator<(const COleCurrency& cur) const;
BOOL operator>(const COleCurrency& cur) const;
BOOL operator<=(const COleCurrency& cur) const;
BOOL operator>=(const COleCurrency& cur) const;
```

### <a name="remarks"></a>Remarks

> [!NOTE]
>  Возвращаемое значение операций упорядочения ( **<** , **\<=** , **>** , **>=** ) не определено, если состояние любого из операндов равно null или недопустимо. Операторы равенства (`==`, `!=`) учитывают состояние операндов.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]

##  <a name="colecurrencysetcurrency"></a><a name="setcurrency"></a>COleCurrency:: Сеткурренци

Вызовите эту функцию члена, чтобы задать единицы и дробную часть данного объекта `COleCurrency`.

```
void SetCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>Параметры

*нунитс*, *нфрактионалунитс* указывает единицы и дробную часть значения, которое копируется в этот `COleCurrency` объект.

### <a name="remarks"></a>Remarks

Если абсолютное значение дробной части больше 10 000, в единицы измерения вносится соответствующая корректировка, как показано в третьем из следующих примеров.

Обратите внимание, что единицы и дробная часть указываются с помощью длинных значений со знаком. В четвертом из следующих примеров показано, что происходит, когда параметры имеют разные знаки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]

##  <a name="colecurrencysetstatus"></a><a name="setstatus"></a>COleCurrency:: SetStatus

Вызовите эту функцию-член, чтобы задать состояние (допустимость) этого `COleCurrency` объекта.

```
void SetStatus(CurrencyStatus  status  );
```

### <a name="parameters"></a>Параметры

*status*<br/>
Новое состояние для данного объекта `COleCurrency`.

### <a name="remarks"></a>Remarks

Значение параметра *Status* определяется типом перечисления `CurrencyStatus`, который определен в классе `COleCurrency`.

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

Краткое описание этих значений состояния см. в следующем списке:

- `COleCurrency::valid` указывает, что этот `COleCurrency` объект является допустимым.

- `COleCurrency::invalid` указывает, что этот `COleCurrency` объект является недопустимым; то есть его значение может быть неправильным.

- `COleCurrency::null` указывает, что этот `COleCurrency` объект имеет значение null, то есть для этого объекта не было предоставлено значение. (Значение NULL в базе данных имеет значение «не имеет значения», а в отличие от C++ значения NULL).

> [!CAUTION]
>  Эта функция предназначена для расширенных ситуаций программирования. Эта функция не изменяет данные в этом объекте. Чаще всего он используется для установки состояния в значение null или недопустимо. Обратите внимание, что оператор присваивания ( [operator =](#operator_eq)) и [сеткурренци](#setcurrency) устанавливают для состояния значение объекта, основанного на исходных значениях.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleVariant](../../mfc/reference/colevariant-class.md)
