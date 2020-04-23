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
ms.openlocfilehash: cc69143101c5d00d4f9a689bd02abdd9596e5b53
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753920"
---
# <a name="colecurrency-class"></a>Класс COleCurrency

Инкапсулирует тип данных `CURRENCY` автоматизации OLE.

## <a name="syntax"></a>Синтаксис

```
class COleCurrency
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeCurrency::COleCurrency](#colecurrency)|Формирует объект `COleCurrency`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeCurrency::Формат](#format)|Генерирует отформатированный строковый `COleCurrency` репрезентации объекта.|
|[ColeCurrency::GetStatus](#getstatus)|Получает статус (действительность) `COleCurrency` этого объекта.|
|[ColeCurrency::ParseCurrency](#parsecurrency)|Читает значение CURRENCY из строки `COleCurrency`и устанавливает значение .|
|[ColeCurrency::SetCurrency](#setcurrency)|Устанавливает значение этого `COleCurrency` объекта.|
|[ColeCurrency::SetStatus](#setstatus)|Устанавливает статус (действительность) `COleCurrency` для этого объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Оператор](#operator_eq)|Копирует `COleCurrency` значение.|
|[оператор No, -](#operator_plus_minus)|Добавляет, вычитает и изменяет `COleCurrency` знак значений.|
|[оператором, --](#operator_plus_minus_eq)|Добавляет и вычитает `COleCurrency` значение `COleCurrency` из этого объекта.|
|[оператор К/](#operator_star)|Масштабирует `COleCurrency` значение по величине значения.|
|[оператора, /)](#operator_star_div_eq)|Масштабирует `COleCurrency` это значение по принципу «все же».|
|[оператор <<](#operator_stream)|Выводы `COleCurrency` значение `CArchive` или `CDumpContext`.|
|[оператор >>](#operator_stream)|Ввод `COleCurrency` объекта `CArchive`из .|
|[оператор CURRENCY](#operator_currency)|Преобразует `COleCurrency` значение в CURRENCY.|
|[оператор, <, <и т.д.](#colecurrency_relational_operators)|Сравнивает `COleCurrency` два значения.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[ColeCurrency:::m_cur](#m_cur)|Содержит базовый CURRENCY `COleCurrency` для этого объекта.|
|[ColeCurrency::m_status](#m_status)|Содержит статус этого `COleCurrency` объекта.|

## <a name="remarks"></a>Remarks

`COleCurrency`не имеет базового класса.

CURRENCY реализован в виде 8 байт, двух дополнением целых значение масштабируется на 10000. Это позволяет получить число с фиксированной запятой с 15 разрядами слева от десятичной запятой и 4 разрядами справа от нее. Тип данных CURRENCY чрезвычайно полезен для расчетов с участием денег или для любого расчета с фиксированной точкой, где важна точность. Это один из возможных `VARIANT` типов для типа данных АВТОМАТИЗАЦИи OLE.

`COleCurrency`также реализует некоторые основные арифметические операции для этого типа фиксированной точки. Поддерживаемые операции были выбраны для управления ошибками округления, которые возникают при расчетах с фиксированной точкой.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`COleCurrency`

## <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="colecurrencycolecurrency"></a><a name="colecurrency"></a>ColeCurrency::COleCurrency

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

*cySrc*<br/>
Значение CURRENCY, подавшееся `COleCurrency` в новый объект.

*curSrc*<br/>
Существующий `COleCurrency` объект, который должен `COleCurrency` быть скопирован в новый объект.

*varSrc*<br/>
Существующая `VARIANT` структура данных `COleVariant` (возможно, объект), которая должна быть преобразована в `COleCurrency` валютную стоимость (VT_CY) и скопирована в новый объект.

*nUnits,* *nFractionalUnits* указывают единицы и дробную часть (в 1/10,000)' значения, подаваемого в новый `COleCurrency` объект.

### <a name="remarks"></a>Remarks

Все эти конструкторы создают `COleCurrency` новые объекты, инициализированные к заданному значению. Ниже приводится краткое описание каждого из этих конструкторов. Если не указано иное, статус нового `COleCurrency` элемента устанавливается в действии.

- COleCurrency() строит `COleCurrency` объект, инициализированный до 0 (ноль).

- COleCurrency(`cySrc`) строит `COleCurrency` объект из значения [CURRENCY.](/windows/win32/api/wtypes/ns-wtypes-cy~r1)

- COleCurrency(`curSrc`) строит `COleCurrency` объект из `COleCurrency` существующего объекта. Новый объект имеет тот же статус, что и исходный объект.

- COleCurrency(`varSrc`) Строит `COleCurrency` объект. Попытки конвертировать [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) структуру `COleVariant` VARIANT или объект в валютное (VT_CY) значение. Если это преобразование успешно, преобразованное `COleCurrency` значение скопировано в новый объект. В противном случае значение `COleCurrency` объекта устанавливается до нуля (0), а его статус - недействительным.

- COleCurrency(`nUnits` `nFractionalUnits`, ) `COleCurrency` строит объект из указанных численных компонентов. Если абсолютное значение дробной части превышает 10 000, то в единицы производится соответствующая корректировка. Обратите внимание, что единицы и дробная часть определяются подписанными длинными значениями.

Для получения дополнительной информации смотрите записи [CURRENCY](/windows/win32/api/wtypes/ns-wtypes-cy~r1) и [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) в SDK Windows.

### <a name="example"></a>Пример

Следующие примеры показывают эффекты конструкторов с нулевым параметром и двумя параметрами:

[!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]

## <a name="colecurrencyformat"></a><a name="format"></a>ColeCurrency::Формат

Вызовите эту функцию участника, чтобы создать отформатированный представление стоимости валюты.

```
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const;
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Отосевание флагов для настроек локализации. Только следующий флаг имеет отношение к валюте:

- LOCALE_NOUSEROVERRIDE использовать настройки локального локального по умолчания системы, а не пользовательские настройки пользователя.

*lcid*<br/>
Указывает идентификатор локализации для использования для преобразования.

### <a name="return-value"></a>Возвращаемое значение

A, `CString` содержащий отформатированную валютную стоимость.

### <a name="remarks"></a>Remarks

Он форматирует значение, используя спецификации локального языка (locale ID). Символ валюты не включен в возвращенное значение. Если состояние этого `COleCurrency` объекта является нулевым, значение возврата является пустой строкой. Если статус недействителен, строка возврата указывается ресурсом строки IDS_INVALID_CURRENCY.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]

## <a name="colecurrencygetstatus"></a><a name="getstatus"></a>ColeCurrency::GetStatus

Вызовите эту функцию участника, чтобы получить `COleCurrency` статус (действительность) данного объекта.

```
CurrencyStatus GetStatus() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает статус этого `COleCurrency` значения.

### <a name="remarks"></a>Remarks

Значение возврата определяется `CurrencyStatus` перечисленным типом, который определяется в `COleCurrency` классе.

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

Краткое описание этих значений статуса см.

- `COleCurrency::valid`Означает, `COleCurrency` что этот объект является действительным.

- `COleCurrency::invalid`Указывает, `COleCurrency` что этот объект является недействительным; то есть, его значение может быть неправильным.

- `COleCurrency::null`Означает, `COleCurrency` что этот объект является нулевым, т.е. что для этого объекта не было поставлено значение. (Это "нулевой" в базе данных смысле "не имеет значения", в отличие от СЗ NULL.)

Статус `COleCurrency` объекта является недействительным в следующих случаях:

- Если его значение устанавливается `COleVariant` из VARIANT или значения, которое не может быть преобразовано в валютную стоимость.

- Если этот объект испытал переполнение или недопоге во `+=` время ** \* **операции арифметического назначения, например, или .

- Если недействительное значение было назначено этому объекту.

- Если статус этого объекта был явно установлен на недействительным с помощью [SetStatus](#setstatus).

Для получения дополнительной информации об операциях, которые могут привести статус к инвалидности, см.

- [COleCurrency](#colecurrency)

- [Оператор](#operator_eq)

- [Оператор - -](#operator_plus_minus)

- [оператора и --](#operator_plus_minus_eq)

- [Оператор q /](#operator_star)

- [оператора и /)](#operator_star_div_eq)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]

## <a name="colecurrencym_cur"></a><a name="m_cur"></a>ColeCurrency:::m_cur

Базовая структура [CURRENCY](/windows/win32/api/wtypes/ns-wtypes-cy~r1) `COleCurrency` для этого объекта.

### <a name="remarks"></a>Remarks

> [!CAUTION]
> Изменение значения в `CURRENCY` структуре, доступ к которым указателем, возвращенному `COleCurrency` этой функцией, изменит значение этого объекта. Статус этого `COleCurrency` объекта не изменяется.

Для получения дополнительной информации, смотрите запись [CURRENCY](/windows/win32/api/wtypes/ns-wtypes-cy~r1) в Windows SDK.

## <a name="colecurrencym_status"></a><a name="m_status"></a>ColeCurrency::m_status

Тип этого члена данных является перечисленным `CurrencyStatus`типом, который `COleCurrency` определяется в классе.

```
enum CurrencyStatus{
    valid = 0,
    invalid = 1,
    null = 2,
};
```

### <a name="remarks"></a>Remarks

Краткое описание этих значений статуса см.

- `COleCurrency::valid`Означает, `COleCurrency` что этот объект является действительным.

- `COleCurrency::invalid`Указывает, `COleCurrency` что этот объект является недействительным; то есть, его значение может быть неправильным.

- `COleCurrency::null`Означает, `COleCurrency` что этот объект является нулевым, т.е. что для этого объекта не было поставлено значение. (Это "нулевой" в базе данных смысле "не имеет значения", в отличие от СЗ NULL.)

Статус `COleCurrency` объекта является недействительным в следующих случаях:

- Если его значение устанавливается `COleVariant` из VARIANT или значения, которое не может быть преобразовано в валютную стоимость.

- Если этот объект испытал переполнение или недопоге во `+=` время ** \* **операции арифметического назначения, например, или .

- Если недействительное значение было назначено этому объекту.

- Если статус этого объекта был явно установлен на недействительным с помощью [SetStatus](#setstatus).

Для получения дополнительной информации об операциях, которые могут привести статус к инвалидности, см.

- [COleCurrency](#colecurrency)

- [Оператор](#operator_eq)

- [оператор No, -](#operator_plus_minus)

- [оператором, --](#operator_plus_minus_eq)

- [оператор К/](#operator_star)

- [оператора, /)](#operator_star_div_eq)

> [!CAUTION]
> Этот член данных предназначен для передовых ситуаций программирования. Вы должны использовать внеочередные функции членов [GetStatus](#getstatus) и [SetStatus.](#setstatus) Дополнительные предостережения читайте `SetStatus` в вопросе о явном настройке этого участника данных.

## <a name="colecurrencyoperator-"></a><a name="operator_eq"></a>ColeCurrency::оператор

Эти перегруженные операторы назначения копируют `COleCurrency` исходное значение валюты в этом объекте.

```
const COleCurrency& operator=(CURRENCY cySrc);
const COleCurrency& operator=(const COleCurrency& curSrc);
const COleCurrency& operator=(const VARIANT& varSrc);
```

### <a name="remarks"></a>Remarks

Краткое описание каждого оператора:

- **оператор No (** `cySrc` **)** Значение `CURRENCY` скопировано `COleCurrency` в объект и его статус установлен в действии.

- **оператор No (** `curSrc` **)** Значение и статус операнд, существующего `COleCurrency` объекта копируются в этот `COleCurrency` объект.

- **оператор No** *(varSrc* **)** Если преобразование `VARIANT` значения (или объекта [COleVariant)](../../mfc/reference/colevariant-class.md) в валюту () `VT_CY`является успешным, конвертированное значение скопировано в этот `COleCurrency` объект и его статус установлен в действии. Если преобразование не является успешным, значение `COleCurrency` объекта устанавливается до 0, а его статус - недействительным.

Для получения дополнительной информации смотрите записи [CURRENCY](/windows/win32/api/wtypes/ns-wtypes-cy~r1) и [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) в SDK Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]

## <a name="colecurrencyoperator---"></a><a name="operator_plus_minus"></a>ColeCurrency::оператор No, -

Эти операторы позволяют добавлять `COleCurrency` и вычесть два значения друг к `COleCurrency` другу и друг от друга и изменить знак значения.

```
COleCurrency operator+(const COleCurrency& cur) const;
COleCurrency operator-(const COleCurrency& cur) const;
COleCurrency operator-() const;
```

### <a name="remarks"></a>Remarks

Если какая-либо из действий является нулевой, `COleCurrency` статус полученного значения является нулевым.

Если арифметическая операция переполнена, `COleCurrency` полученное значение является недействительным.

Если операнд является недействительным, а другой не является недействительным, статус полученного `COleCurrency` значения является недействительным.

Для получения дополнительной информации об действительных, недействительных и недействительных значениях статуса [m_status](#m_status) см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]

## <a name="colecurrencyoperator---"></a><a name="operator_plus_minus_eq"></a>ColeCurrency::оператор , -»

Разрешить добавлять и вычесть `COleCurrency` значение к `COleCurrency` этому объекту и из нее.

```
const COleCurrency& operator+=(const COleCurrency& cur);
const COleCurrency& operator-=(const COleCurrency& cur);
```

### <a name="remarks"></a>Remarks

Если какая-либо из действий недействительна, статус этого `COleCurrency` объекта сведен к нулю.

Если арифметическая операция переполнена, статус `COleCurrency` этого объекта становится недействительным.

Если какая-либо из действий недействительна, а другая `COleCurrency` не является нулевой, статус этого объекта устанавливается недействительным.

Для получения дополнительной информации об действительных, недействительных и недействительных значениях статуса [m_status](#m_status) см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]

## <a name="colecurrencyoperator--and-"></a><a name="operator_star"></a>ColeCurrency::оператор \* и /

Позволяет масштабировать `COleCurrency` значение по интегральному значению.

```
COleCurrency operator*(long nOperand) const;
COleCurrency operator/(long nOperand) const;
```

### <a name="remarks"></a>Remarks

Если `COleCurrency` операнд является нулевым, статус `COleCurrency` полученного значения является нулевым.

Если арифметическая операция переполнена или недотечна, состояние полученного `COleCurrency` значения является недействительным.

Если `COleCurrency` операнд недействителен, статус полученного `COleCurrency` значения является недействительным.

Для получения дополнительной информации об действительных, недействительных и недействительных значениях статуса [m_status](#m_status) см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]

## <a name="colecurrencyoperator--"></a><a name="operator_star_div_eq"></a>COleCurrency::оператор \*, /)

Позволяет масштабировать `COleCurrency` это значение на целостное значение.

```
const COleCurrency& operator*=(long nOperand);
const COleCurrency& operator/=(long nOperand);
```

### <a name="remarks"></a>Remarks

Если `COleCurrency` операнд является нулевым, `COleCurrency` статус этого объекта устанавливается в ней.

Если арифметическая операция переполнена, статус `COleCurrency` этого объекта становится недействительным.

Если `COleCurrency` операнд недействителен, статус `COleCurrency` этого объекта устанавливается недействительным.

Для получения дополнительной информации об действительных, недействительных и недействительных значениях статуса [m_status](#m_status) см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]

## <a name="colecurrencyoperator-ltlt-gtgt"></a><a name="operator_stream"></a>ColeCurrency::оператор &lt; &lt;,&gt;&gt;

Поддерживает диагностический демпинг и хранение в архиве.

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

Извлечение **>>**() оператор поддерживает загрузку из архива.

## <a name="colecurrencyoperator-currency"></a><a name="operator_currency"></a>ColeCurrency::оператор CURRENCY

Возвращает `CURRENCY` структуру, значение которой `COleCurrency` скопировано с этого объекта.

```
operator CURRENCY() const;
```

### <a name="remarks"></a>Remarks

## <a name="colecurrencyparsecurrency"></a><a name="parsecurrency"></a>ColeCurrency::ParseCurrency

Вызовите эту функцию участника, чтобы разобрать строку для чтения валютного значения.

```
BOOL ParseCurrency(
    LPCTSTR lpszCurrency,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT);

throw(CMemoryException*);
throw(COleException*);
```

### <a name="parameters"></a>Параметры

*lpszCurrency*<br/>
Указатель на нулевую строку, которая должна быть разогнана.

*dwFlags*<br/>
Отосевает флаги для настроек локализации, возможно, следующий флаг:

- LOCALE_NOUSEROVERRIDE использовать настройки локального локального по умолчания системы, а не пользовательские настройки пользователя.

*lcid*<br/>
Указывает идентификатор локализации для использования для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если строка была успешно преобразована в валютное значение, в противном случае 0.

### <a name="remarks"></a>Remarks

Он использует спецификации локального языка (локальные идол) для значения ненумерных символов в строке исходного кода.

Для обсуждения значений идентификатора [локализации](/previous-versions/windows/desktop/automat/supporting-multiple-national-languages)см.

Если строка была успешно преобразована в валютную стоимость, значение этого `COleCurrency` объекта устанавливается к этому значению и его статус действителен.

Если строка не может быть преобразована в валюту или если произошел `COleCurrency` численный переполнение, статус этого объекта является недействительным.

Если преобразование строки не удалось из-за ошибок распределения памяти, эта функция бросает [CMemoryException](../../mfc/reference/cmemoryexception-class.md). В любом другом состоянии ошибки эта функция бросает [COleException.](../../mfc/reference/coleexception-class.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]

## <a name="colecurrency-relational-operators"></a><a name="colecurrency_relational_operators"></a>ColeCurrency реляционные операторы

Сравните две валютные значения и возврат ненулевой, если условие верно; в противном случае 0.

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
> Значение возврата операций заказа **<** ** \< **(, **>** **>=**, ) не определено, если статус либо операции является недействительным или недействительным. Операторы по `==` `!=`вопросам равенства (, рассматривают статус операнд.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]

## <a name="colecurrencysetcurrency"></a><a name="setcurrency"></a>ColeCurrency::SetCurrency

Вызов исчерпайте эту функцию участника `COleCurrency` для установки единиц и дробной части этого объекта.

```cpp
void SetCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>Параметры

*nUnits,* *nFractionalUnits* указывают единицы и дробную часть (в 1/10,000)' `COleCurrency` значения, подаваемые в этот объект.

### <a name="remarks"></a>Remarks

Если абсолютное значение дробной части превышает 10 000, то соответствующая корректировка производится в единицах, как показано в третьем из следующих примеров.

Обратите внимание, что единицы и дробная часть определяются подписанными длинными значениями. Четвертый из следующих примеров показывает, что происходит, когда параметры имеют различные признаки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]

## <a name="colecurrencysetstatus"></a><a name="setstatus"></a>ColeCurrency::SetStatus

Вызовите эту функцию участника, чтобы `COleCurrency` установить статус (действительность) этого объекта.

```cpp
void SetStatus(CurrencyStatus  status  );
```

### <a name="parameters"></a>Параметры

*status*<br/>
Новый статус `COleCurrency` для этого объекта.

### <a name="remarks"></a>Remarks

Значение параметра *состояния* определяется `CurrencyStatus` перечисленным типом, который `COleCurrency` определяется в классе.

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

Краткое описание этих значений статуса см.

- `COleCurrency::valid`Означает, `COleCurrency` что этот объект является действительным.

- `COleCurrency::invalid`Указывает, `COleCurrency` что этот объект является недействительным; то есть, его значение может быть неправильным.

- `COleCurrency::null`Означает, `COleCurrency` что этот объект является нулевым, т.е. что для этого объекта не было поставлено значение. (Это "нулевой" в базе данных смысле "не имеет значения", в отличие от СЗ NULL.)

> [!CAUTION]
> Эта функция предназначена для передовых ситуаций программирования. Эта функция не изменяет данные в этом объекте. Чаще всего он будет использоваться для установки статуса недействительным или недействительным. Обратите внимание, что оператор назначения [(оператор )](#operator_eq)и [SetCurrency](#setcurrency) устанавливают статус объекта на основе исходного значения (ы).

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleVariant](../../mfc/reference/colevariant-class.md)
