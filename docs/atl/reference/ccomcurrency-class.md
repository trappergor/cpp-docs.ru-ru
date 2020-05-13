---
title: Класс CComCurrency
ms.date: 11/04/2016
f1_keywords:
- CComCurrency
- ATLCUR/ATL::CComCurrency
- ATLCUR/ATL::CComCurrency::CComCurrency
- ATLCUR/ATL::CComCurrency::GetCurrencyPtr
- ATLCUR/ATL::CComCurrency::GetFraction
- ATLCUR/ATL::CComCurrency::GetInteger
- ATLCUR/ATL::CComCurrency::Round
- ATLCUR/ATL::CComCurrency::SetFraction
- ATLCUR/ATL::CComCurrency::SetInteger
- ATLCUR/ATL::CComCurrency::m_currency
helpviewer_keywords:
- CComCurrency class
ms.assetid: a1c3d10a-bba6-40cc-8bcf-aed9023c8a9e
ms.openlocfilehash: 541944e03e9caf6cba15612cf9e7cbbd239555ca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327942"
---
# <a name="ccomcurrency-class"></a>Класс CComCurrency

`CComCurrency` содержит методы и операторы для создания объекта CURRENCY и управления им.

## <a name="syntax"></a>Синтаксис

```
class CComCurrency
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComCurrency::CComCurrency](#ccomcurrency)|Конструктор объекта `CComCurrency`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComCurrency::GetCurrencyPtr](#getcurrencyptr)|Возвращает адрес элемента данных `m_currency`.|
|[CComCurrency::GetFraction](#getfraction)|Вызовите этот метод для возврата дробной части объекта `CComCurrency`.|
|[CComCurrency::GetInteger](#getinteger)|Вызовите этот метод для возврата целой части объекта `CComCurrency`.|
|[CComCurrency::Round](#round)|Вызовите этот метод для округления объекта `CComCurrency` до ближайшего целого значения.|
|[CComCurrency::SetFraction](#setfraction)|Вызовите этот метод для установки дробной части объекта `CComCurrency`.|
|[CComCurrency::SetInteger](#setinteger)|Вызовите этот метод для установки целой части объекта `CComCurrency`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CComCurrency::оператор -](#operator_-)|Этот оператор используется для вычитания объекта `CComCurrency`.|
|[CComCurrency::оператор !](#operator_neq)|Проверяет неравенство двух объектов `CComCurrency`.|
|[CComCurrency::оператор](#operator_star)|Этот оператор используется для умножения объекта `CComCurrency`.|
|[CComCurrency::Оператор](#operator_star_eq)|Этот оператор используется для умножения объекта `CComCurrency` и назначения ему результата.|
|[CComCurrency:оператор /](#operator_div)|Этот оператор используется для деления объекта `CComCurrency`.|
|[CComCurrency:оператор /](#operator_div_eq)|Этот оператор используется для деления объекта `CComCurrency` и назначения ему результата.|
|[CComCurrency::оператор](#operator_add)|Этот оператор используется для сложения объекта `CComCurrency`.|
|[CComCurrency::operator +=](#operator_add_eq)|Этот оператор используется для сложения объекта `CComCurrency` и назначения ему результата.|
|[CComCurrency::оператор <](#operator_lt)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить меньший из них.|
|[CComCurrency::оператор <](#operator_lt_eq)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или меньший из них.|
|[CComCurrency::оператор](#operator_eq)|Этот оператор присваивает объекту `CComCurrency` новое значение.|
|[CComCurrency:оператор -](#operator_-_eq)|Этот оператор используется для вычитания объекта `CComCurrency` и назначения ему результата.|
|[CComCurrency::оператор](#operator_eq_eq)|Этот оператор сравнивает два объекта `CComCurrency` на равенство.|
|[CComCurrency::оператор >](#operator_gt)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить больший из них.|
|[CComCurrency::оператор >](#operator_gt_eq)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или больший из них.|
|[CComCurrency::оператор CURRENCY](#operator_currency)|Отбрасывает объект CURRENCY.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComCurrency::m_currency](#m_currency)|Переменная CURRENCY, созданная экземпляром класса.|

## <a name="remarks"></a>Remarks

`CComCurrency` — это оболочка для типа данных CURRENCY. CURRENCY реализуется как целое 8-байтное значение в дополнительном коде, умноженное на 10 000. Это позволяет получить число с фиксированной запятой с 15 разрядами слева от десятичной запятой и 4 разрядами справа от нее. Тип данныхCURRENCY крайне полезен для денежных расчетов или расчетов с фиксированной запятой, когда важна точность.

Обертка `CComCurrency` реализует арифметические, назначения и сравнительные операции для этого типа фиксированной точки. Поддерживаемые приложения были выбраны для управления ошибками округления, которые могут возникнуть во время вычислений с фиксированной запятой.

Объект `CComCurrency` предоставляет доступ к числа с обеих сторон от десятичного разделителя в формате из двух компонентов: целого компонента со знаком, в котором хранится значение слева от десятичной запятой, и дробного компонента, в котором хранится значение справа от десятичной запятой. Дробная часть хранится в системе как целое значение от —9 999 (CY_MIN_FRACTION) до +9 999 (CY_MAX_FRACTION). Метод [CComCurrency::GetFraction](#getfraction) возвращает значение, масштабированное в 10000 (CY_SCALE).

При указании целого и дробных компонентов `CComCurrency` объекта помните, что дробный компонент представляет собой число в диапазоне от 0 до 9999. Это важно при работе с валютой, например долларом США, когда суммы выражаются с использованием только двух значащих цифр после запятой. Хотя две последние цифры не отображаются, их необходимо учитывать.

|Значение|Возможные значения CComCurrency|
|-----------|---------------------------------------|
|$10.50|CComCurrency (10,5000) *или* CComCurrency (10.50)|
|$10.05|CComCurrency (10 500) *или* CComCurrency (10.05)|

Значения CY_MIN_FRACTION, CY_MAX_FRACTION и  CY_SCALE определены в файле atlcur.h.

## <a name="requirements"></a>Требования

**Заголовок:** atlcur.h

## <a name="ccomcurrencyccomcurrency"></a><a name="ccomcurrency"></a>CComCurrency::CComCurrency

Конструктор.

```
CComCurrency() throw();
CComCurrency(const CComCurrency& curSrc) throw();
CComCurrency(CURRENCY cySrc) throw();
CComCurrency(DECIMAL dSrc);
CComCurrency(ULONG ulSrc);
CComCurrency(USHORT usSrc);
CComCurrency(CHAR cSrc);
CComCurrency(DOUBLE dSrc);
CComCurrency(FLOAT fSrc);
CComCurrency(LONG lSrc);
CComCurrency(SHORT sSrc);
CComCurrency(BYTE bSrc);
CComCurrency(LONGLONG nInteger, SHORT nFraction);
explicit CComCurrency(LPDISPATCH pDispSrc);
explicit CComCurrency(const VARIANT& varSrc);
explicit CComCurrency(LPCWSTR szSrc);
explicit CComCurrency(LPCSTR szSrc);
```

### <a name="parameters"></a>Параметры

*curSrc*<br/>
Существующий объект `CComCurrency`.

*cySrc*<br/>
Переменная типа CURRENCY.

*bSrc*, *dSrc*, *fSrc*, *lSrc*, *sSrc*, *ulSrc, usSrc*<br/>
Начальное значение, присвоенное переменной `m_currency`члена.

*cSrc*<br/>
Символ, содержащий исходное значение `m_currency`переменной участника.

*nInteger*, *nФракция*<br/>
Несемеиальные и дробные компоненты начальной денежной стоимости. Дополнительную информацию можно узнать в обзоре [CComCurrency.](../../atl/reference/ccomcurrency-class.md)

*pDispSrc*<br/>
Указатель. `IDispatch`

*varSrc*<br/>
Переменная типа VARIANT. Локоть текущего потока используется для выполнения преобразования.

*szSrc*<br/>
Строка Unicode или ANSI, содержащая начальное значение. Локоть текущего потока используется для выполнения преобразования.

### <a name="remarks"></a>Remarks

Конструктор устанавливает начальное значение [CCom m_currencyCurrency](#m_currency)и принимает широкий спектр типов данных, включая целые числа, строки, номера плавающих точек, переменные CURRENCY и другие `CComCurrency` объекты. Если значение не `m_currency` предусмотрено, устанавливается до 0.

В случае ошибки, такой как переполнение, конструкторы не имеют пустой спецификации `AtlThrow` исключения **(бросок))** вызова с HRESULT, описывающим ошибку.

При использовании плавающей точки или двойных значений `CComCurrency(10.50)` для присвоения значения обратите внимание, что это `CComCurrency(10,5000)` эквивалентно, а не. `CComCurrency(10,50)`

## <a name="ccomcurrencygetcurrencyptr"></a><a name="getcurrencyptr"></a>CComCurrency::GetCurrencyPtr

Возвращает адрес элемента данных `m_currency`.

```
CURRENCY* GetCurrencyPtr() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает адрес участника `m_currency` данных

## <a name="ccomcurrencygetfraction"></a><a name="getfraction"></a>CComCurrency::GetFraction

Вызовите этот метод, чтобы `CComCurrency` вернуть дробный компонент объекта.

```
SHORT GetFraction() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает дробный компонент `m_currency` члена данных.

### <a name="remarks"></a>Remarks

Дробный компонент представляет собой 4-значное значение между -9999 (CY_MIN_FRACTION) и 9999 евро (CY_MAX_FRACTION). `GetFraction`возвращает это значение, уменьшенное на 10000 (CY_SCALE). Значения CY_MIN_FRACTION, CY_MAX_FRACTION и CY_SCALE определяются в atlcur.h.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#50](../../atl/codesnippet/cpp/ccomcurrency-class_1.cpp)]

## <a name="ccomcurrencygetinteger"></a><a name="getinteger"></a>CComCurrency::GetInteger

Вызовите этот метод, чтобы получить `CComCurrency` компонент степле объекта.

```
LONGLONG GetInteger() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает компонент несхожего члена `m_currency` данных.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#51](../../atl/codesnippet/cpp/ccomcurrency-class_2.cpp)]

## <a name="ccomcurrencym_currency"></a><a name="m_currency"></a>CComCurrency::m_currency

Член данных CURRENCY.

```
CURRENCY m_currency;
```

### <a name="remarks"></a>Remarks

Этот участник держит валюту, доступ к которой и манипулируемый методами этого класса.

## <a name="ccomcurrencyoperator--"></a><a name="operator_-"></a>CComCurrency::оператор -

Этот оператор используется для вычитания объекта `CComCurrency`.

```
CComCurrency operator-() const;
CComCurrency operator-(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*Cur*<br/>
Объект `CComCurrency` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CComCurrency` объект, представляющий результат вычитания. В случае ошибки, например переполнения, `AtlThrow` этот оператор вызывает с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#55](../../atl/codesnippet/cpp/ccomcurrency-class_3.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_neq"></a>CComCurrency::оператор !

Этот оператор сравнивает два объекта для неравенства.

```
bool operator!= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*Cur*<br/>
Сравниваемый объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если сравниваемый `CComCurrency` элемент не равен объекту; в противном случае, FALSE.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#56](../../atl/codesnippet/cpp/ccomcurrency-class_4.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_star"></a>CComCurrency::оператор

Этот оператор используется для умножения объекта `CComCurrency`.

```
CComCurrency operator*(long nOperand) const;
CComCurrency operator*(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*nOperand*<br/>
Коэффициент.

*Cur*<br/>
Объект `CComCurrency` используется в качестве множителя.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CComCurrency` объект, представляющий результат умножения. В случае ошибки, например переполнения, `AtlThrow` этот оператор вызывает с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#57](../../atl/codesnippet/cpp/ccomcurrency-class_5.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_star_eq"></a>CComCurrency::оператор\*=

Этот оператор используется для умножения объекта `CComCurrency` и назначения ему результата.

```
const CComCurrency& operator*= (long nOperand);
const CComCurrency& operator*= (const CComCurrency& cur);
```

### <a name="parameters"></a>Параметры

*nOperand*<br/>
Коэффициент.

*Cur*<br/>
Объект `CComCurrency` используется в качестве множителя.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объект. В случае ошибки, например переполнения, `AtlThrow` этот оператор вызывает с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#58](../../atl/codesnippet/cpp/ccomcurrency-class_6.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_div"></a>CComCurrency:оператор /

Этот оператор используется для деления объекта `CComCurrency`.

```
CComCurrency operator/(long nOperand) const;
```

### <a name="parameters"></a>Параметры

*nOperand*<br/>
Делитель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CComCurrency` объект, представляющий результат разделения. Если диверсия 0, утверждение сбой произойдет.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#59](../../atl/codesnippet/cpp/ccomcurrency-class_7.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_div_eq"></a>CComCurrency:оператор /

Этот оператор используется для деления объекта `CComCurrency` и назначения ему результата.

```
const CComCurrency& operator/= (long nOperand);
```

### <a name="parameters"></a>Параметры

*nOperand*<br/>
Делитель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объект. Если диверсия 0, утверждение сбой произойдет.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#60](../../atl/codesnippet/cpp/ccomcurrency-class_8.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_add"></a>CComCurrency::оператор

Этот оператор используется для сложения объекта `CComCurrency`.

```
CComCurrency operator+(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*Cur*<br/>
Объект, `CComCurrency` который будет добавлен к исходной объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CComCurrency` объект, представляющий результат добавления. В случае ошибки, например переполнения, `AtlThrow` этот оператор вызывает с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#61](../../atl/codesnippet/cpp/ccomcurrency-class_9.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_add_eq"></a>CComCurrency::Оператор

Этот оператор используется для сложения объекта `CComCurrency` и назначения ему результата.

```
const CComCurrency& operator+= (const CComCurrency& cur);
```

### <a name="parameters"></a>Параметры

*Cur*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объект. В случае ошибки, например переполнения, `AtlThrow` этот оператор вызывает с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#62](../../atl/codesnippet/cpp/ccomcurrency-class_10.cpp)]

## <a name="ccomcurrencyoperator-lt"></a><a name="operator_lt"></a>CComCurrency::оператор&lt;

Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить меньший из них.

```
bool operator<(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*Cur*<br/>
Объект `CComCurrency` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если первый объект меньше второго, FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#63](../../atl/codesnippet/cpp/ccomcurrency-class_11.cpp)]

## <a name="ccomcurrencyoperator-lt"></a><a name="operator_lt_eq"></a>CComCurrency::оператор&lt;=

Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или меньший из них.

```
bool operator<= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*Cur*<br/>
Объект `CComCurrency` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если первый объект меньше или равен второму, FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#64](../../atl/codesnippet/cpp/ccomcurrency-class_12.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_eq"></a>CComCurrency::оператор

Этот оператор присваивает объекту `CComCurrency` новое значение.

```
const CComCurrency& operator= (const CComCurrency& curSrc) throw();
const CComCurrency& operator= (CURRENCY cySrc) throw();
const CComCurrency& operator= (FLOAT fSrc);
const CComCurrency& operator= (SHORT sSrc);
const CComCurrency& operator= (LONG lSrc);
const CComCurrency& operator= (BYTE bSrc);
const CComCurrency& operator= (USHORT usSrc);
const CComCurrency& operator= (DOUBLE dSrc);
const CComCurrency& operator= (CHAR cSrc);
const CComCurrency& operator= (ULONG ulSrc);
const CComCurrency& operator= (DECIMAL dSrc);
```

### <a name="parameters"></a>Параметры

*curSrc*<br/>
Объект `CComCurrency` .

*cySrc*<br/>
Переменная типа CURRENCY.

*sSrc*, *fSrc*, *lSrc*, *bSrc*, *usSrc*, *dSrc*, *cSrc*, *ulSrc,* *dSrc*<br/>
Числовое значение для присвоения объекту. `CComCurrency`

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объект. В случае ошибки, например переполнения, `AtlThrow` этот оператор вызывает с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#65](../../atl/codesnippet/cpp/ccomcurrency-class_13.cpp)]

## <a name="ccomcurrencyoperator--"></a><a name="operator_-_eq"></a>CComCurrency:оператор -

Этот оператор используется для вычитания объекта `CComCurrency` и назначения ему результата.

```
const CComCurrency& operator-= (const CComCurrency& cur);
```

### <a name="parameters"></a>Параметры

*Cur*<br/>
Объект `CComCurrency` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объект. В случае ошибки, например переполнения, `AtlThrow` этот оператор вызывает с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#66](../../atl/codesnippet/cpp/ccomcurrency-class_14.cpp)]

## <a name="ccomcurrencyoperator-"></a><a name="operator_eq_eq"></a>CComCurrency::оператор

Этот оператор сравнивает два объекта `CComCurrency` на равенство.

```
bool operator== (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*Cur*<br/>
Объект `CComCurrency`, подлежащий сравнению.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если объекты равны `m_currency` (т.е. члены данных, как и рядовые, то в обоих объектах имеют одинаковое значение), FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#67](../../atl/codesnippet/cpp/ccomcurrency-class_15.cpp)]

## <a name="ccomcurrencyoperator-gt"></a><a name="operator_gt"></a>CComCurrency::оператор&gt;

Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить больший из них.

```
bool operator>(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*Cur*<br/>
Объект `CComCurrency` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если первый объект больше второго, FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#68](../../atl/codesnippet/cpp/ccomcurrency-class_16.cpp)]

## <a name="ccomcurrencyoperator-gt"></a><a name="operator_gt_eq"></a>CComCurrency::оператор&gt;=

Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или больший из них.

```
bool operator>= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*Cur*<br/>
Объект `CComCurrency` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если первый объект больше или равен второму, FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#69](../../atl/codesnippet/cpp/ccomcurrency-class_17.cpp)]

## <a name="ccomcurrencyoperator-currency"></a><a name="operator_currency"></a>CComCurrency::оператор CURRENCY

Эти операторы используются `CComCurrency` для отбрасывания объекта в тип данных CURRENCY.

```
operator CURRENCY&() throw();
operator const CURRENCY&() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на объект CURRENCY.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#70](../../atl/codesnippet/cpp/ccomcurrency-class_18.cpp)]

## <a name="ccomcurrencyround"></a><a name="round"></a>CComCurrency::Round

Позвоните по этому методу, чтобы округлить валюту до определенного количества десятичных мест.

```
HRESULT Roundint nDecimals);
```

### <a name="parameters"></a>Параметры

*nDecimals*<br/>
Количество цифр, к `m_currency` которым будет округлено, в диапазоне от 0 до 4.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#52](../../atl/codesnippet/cpp/ccomcurrency-class_19.cpp)]

## <a name="ccomcurrencysetfraction"></a><a name="setfraction"></a>CComCurrency::SetFraction

Вызовите этот метод для установки дробной части объекта `CComCurrency`.

```
HRESULT SetFraction(SHORT nFraction);
```

### <a name="parameters"></a>Параметры

*nФракция*<br/>
Значение, назначенное дробному компоненту `m_currency` члена данных. Знак дробного компонента должен быть таким же, как и компонент целых, а значение должно быть в диапазоне -9999 (CY_MIN_FRACTION) до 9999 евро (CY_MAX_FRACTION).

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#53](../../atl/codesnippet/cpp/ccomcurrency-class_20.cpp)]

## <a name="ccomcurrencysetinteger"></a><a name="setinteger"></a>CComCurrency::SetInteger

Вызовите этот метод для установки целой части объекта `CComCurrency`.

```
HRESULT SetInteger(LONGLONG nInteger);
```

### <a name="parameters"></a>Параметры

*nИнтегер*<br/>
Значение, назначенное компоненту целых `m_currency` данных члена данных. Знак компонента несколько компонентов должен соответствовать признаку существующего дробного компонента.

*nInteger* должен находиться в диапазоне CY_MIN_INTEGER CY_MAX_INTEGER включительно. Эти значения определяются в atlcur.h.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#54](../../atl/codesnippet/cpp/ccomcurrency-class_21.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс COleCurrency](../../mfc/reference/colecurrency-class.md)<br/>
[Валюты](/windows/win32/api/wtypes/ns-wtypes-cy~r1)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
