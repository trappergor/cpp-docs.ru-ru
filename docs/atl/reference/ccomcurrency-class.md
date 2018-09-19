---
title: Класс CComCurrency | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CComCurrency class
ms.assetid: a1c3d10a-bba6-40cc-8bcf-aed9023c8a9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6eb8c7ed32e780ddaf31dfd6167f59fd55de9da
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116780"
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
|[CComCurrency::operator-](#operator_-)|Этот оператор используется для вычитания объекта `CComCurrency`.|
|[CComCurrency::operator! =](#operator_neq)|Проверяет неравенство двух объектов `CComCurrency`.|
|[CComCurrency::operator *](#operator_star)|Этот оператор используется для умножения объекта `CComCurrency`.|
|[CComCurrency::operator * =](#operator_star_eq)|Этот оператор используется для умножения объекта `CComCurrency` и назначения ему результата.|
|[CComCurrency::operator /](#operator_div)|Этот оператор используется для деления объекта `CComCurrency`.|
|[CComCurrency::operator / =](#operator_div_eq)|Этот оператор используется для деления объекта `CComCurrency` и назначения ему результата.|
|[CComCurrency::operator +](#operator_add)|Этот оператор используется для сложения объекта `CComCurrency`.|
|[CComCurrency::operator +=](#operator_add_eq)|Этот оператор используется для сложения объекта `CComCurrency` и назначения ему результата.|
|[CComCurrency::operator <](#operator_lt)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить меньший из них.|
|[CComCurrency::operator < =](#operator_lt_eq)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или меньший из них.|
|[CComCurrency::operator =](#operator_eq)|Этот оператор присваивает объекту `CComCurrency` новое значение.|
|[CComCurrency::operator-=](#operator_-_eq)|Этот оператор используется для вычитания объекта `CComCurrency` и назначения ему результата.|
|[CComCurrency::operator ==](#operator_eq_eq)|Этот оператор сравнивает два объекта `CComCurrency` на равенство.|
|[CComCurrency::operator >](#operator_gt)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить больший из них.|
|[CComCurrency::operator > =](#operator_gt_eq)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или больший из них.|
|[CComCurrency::operator валюты](#operator_currency)|Приводит объект валюты.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComCurrency::m_currency](#m_currency)|Переменная валюты, созданные экземпляром класса.|

## <a name="remarks"></a>Примечания

`CComCurrency` является оболочкой для типа данных CURRENCY. ВАЛЮТА реализуется как целочисленное значение 8-байтное дополнительном с шагом в 10 000. Это позволяет получить число с фиксированной запятой с 15 разрядами слева от десятичной запятой и 4 разрядами справа от нее. Тип данных CURRENCY очень полезно для денежных расчетов или расчетов с фиксированной запятой когда важна точность.

`CComCurrency` Оболочка реализует операции арифметические операции присваивания и сравнения для этого типа с фиксированной запятой. Поддерживаемые приложения были выбраны для управления ошибками округления, которые могут возникнуть во время вычислений с фиксированной запятой.

Объект `CComCurrency` предоставляет доступ к числа с обеих сторон от десятичного разделителя в формате из двух компонентов: целого компонента со знаком, в котором хранится значение слева от десятичной запятой, и дробного компонента, в котором хранится значение справа от десятичной запятой. Дробная сохраняется целочисленным значением от -9999 (CY_MIN_FRACTION) и 9 (CY_MAX_FRACTION). Метод [CComCurrency::GetFraction](#getfraction) возвращает значение, масштабируется с коэффициентом 10 000 (CY_SCALE).

При указании целого и дробного компонента объекта `CComCurrency` следует помнить, что дробная часть — число в диапазоне от 0 до 9999. Это важно при работе с валютой, например долларом США, когда суммы выражаются с использованием только двух значащих цифр после запятой. Хотя две последние цифры не отображаются, их необходимо учитывать.

|Значение|Возможные значения CComCurrency|
|-----------|---------------------------------------|
|$10.50|CComCurrency(10,5000) *или* CComCurrency(10.50)|
|$10.05|CComCurrency(10,500) *или* CComCurrency(10.05)|

Значения CY_MIN_FRACTION, CY_MAX_FRACTION и CY_SCALE определяются в файле atlcur.h.

## <a name="requirements"></a>Требования

**Заголовок:** atlcur.h

##  <a name="ccomcurrency"></a>  CComCurrency::CComCurrency

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
Переменная типа валюты.

*bSrc*, *dSrc*, *fSrc*, *lSrc*, *sSrc*, *ulSrc usSrc*<br/>
Начальное значение, присваиваемое переменной-члену `m_currency`.

*cSrc*<br/>
Символ, содержащий начальное значение, присваиваемое переменной-члену `m_currency`.

*nInteger*, *nFraction*<br/>
Целого и дробного компонента начального денежные значения. См. в разделе [CComCurrency](../../atl/reference/ccomcurrency-class.md) Дополнительные сведения.

*pDispSrc*<br/>
`IDispatch` Указатель.

*varSrc*<br/>
Переменная типа VARIANT. Языковой стандарт текущего потока используется для выполнения преобразования.

*szSrc*<br/>
Строка Юникода или ANSI, содержащая начальное значение. Языковой стандарт текущего потока используется для выполнения преобразования.

### <a name="remarks"></a>Примечания

Конструктор задает начальное значение [CComCurrency::m_currency](#m_currency)и принимает самые разнообразные типы данных, включая целые числа, строки, числа с плавающей запятой, валюты переменные и другие `CComCurrency` объекты. Если значение не указано, `m_currency` имеет значение 0.

В случае возникновения ошибки, например переполнение, конструкторы, где отсутствует пустую спецификацию исключений (**throw()**) вызвать `AtlThrow` с HRESULT, описывающее ошибку.

При использовании значений с плавающей запятой или типа double для присвоения значения, обратите внимание, что `CComCurrency(10.50)` эквивалентен `CComCurrency(10,5000)` и не `CComCurrency(10,50)`.

##  <a name="getcurrencyptr"></a>  CComCurrency::GetCurrencyPtr

Возвращает адрес элемента данных `m_currency`.

```
CURRENCY* GetCurrencyPtr() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает адрес `m_currency` элемент данных

##  <a name="getfraction"></a>  CComCurrency::GetFraction

Вызовите этот метод для возврата дробной части `CComCurrency` объекта.

```
SHORT GetFraction() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает дробная часть `m_currency` элемента данных.

### <a name="remarks"></a>Примечания

Дробная часть — значение 4-значный целое число от -9999 (CY_MIN_FRACTION) до 9 (CY_MAX_FRACTION). `GetFraction` Возвращает это значение, умноженного на 10000 (CY_SCALE). Значения CY_MIN_FRACTION, CY_MAX_FRACTION и CY_SCALE определяются в файле atlcur.h.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#50](../../atl/codesnippet/cpp/ccomcurrency-class_1.cpp)]

##  <a name="getinteger"></a>  CComCurrency::GetInteger

Вызовите этот метод для получения целой части `CComCurrency` объекта.

```
LONGLONG GetInteger() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает целой части `m_currency` элемент данных.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#51](../../atl/codesnippet/cpp/ccomcurrency-class_2.cpp)]

##  <a name="m_currency"></a>  CComCurrency::m_currency

Элемент данных валюты.

```
CURRENCY m_currency;
```

### <a name="remarks"></a>Примечания

Этот элемент содержит валюте доступ и управлять методами этого класса.

##  <a name="operator_-"></a>  CComCurrency::operator-

Этот оператор используется для вычитания объекта `CComCurrency`.

```
CComCurrency operator-() const;
CComCurrency operator-(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CComCurrency` объект, представляющий результат вычитания. В случае возникновения ошибки, например переполнение, этот оператор вызывает `AtlThrow` с HRESULT, описывающее ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#55](../../atl/codesnippet/cpp/ccomcurrency-class_3.cpp)]

##  <a name="operator_neq"></a>  CComCurrency::operator! =

Этот оператор сравнивает два объекта на предмет их неравенства.

```
bool operator!= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Сравниваемый объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если элемент с которым производится сравнение не равно `CComCurrency` объекта; в противном случае — значение FALSE.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#56](../../atl/codesnippet/cpp/ccomcurrency-class_4.cpp)]

##  <a name="operator_star"></a>  CComCurrency::operator *

Этот оператор используется для умножения объекта `CComCurrency`.

```
CComCurrency operator*(long nOperand) const;
CComCurrency operator*(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*nOperand*<br/>
Множитель.

*cur*<br/>
`CComCurrency` Объект, используемый как множитель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CComCurrency` объект, представляющий результат умножения. В случае возникновения ошибки, например переполнение, этот оператор вызывает `AtlThrow` с HRESULT, описывающее ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#57](../../atl/codesnippet/cpp/ccomcurrency-class_5.cpp)]

##  <a name="operator_star_eq"></a>  CComCurrency::operator \*=

Этот оператор используется для умножения объекта `CComCurrency` и назначения ему результата.

```
const CComCurrency& operator*= (long nOperand);
const CComCurrency& operator*= (const CComCurrency& cur);
```

### <a name="parameters"></a>Параметры

*nOperand*<br/>
Множитель.

*cur*<br/>
`CComCurrency` Объект, используемый как множитель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объекта. В случае возникновения ошибки, например переполнение, этот оператор вызывает `AtlThrow` с HRESULT, описывающее ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#58](../../atl/codesnippet/cpp/ccomcurrency-class_6.cpp)]

##  <a name="operator_div"></a>  CComCurrency::operator /

Этот оператор используется для деления объекта `CComCurrency`.

```
CComCurrency operator/(long nOperand) const;
```

### <a name="parameters"></a>Параметры

*nOperand*<br/>
Делитель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CComCurrency` объект, представляющий результат деления. Если делитель равен 0, возникнет ошибка assert.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#59](../../atl/codesnippet/cpp/ccomcurrency-class_7.cpp)]

##  <a name="operator_div_eq"></a>  CComCurrency::operator / =

Этот оператор используется для деления объекта `CComCurrency` и назначения ему результата.

```
const CComCurrency& operator/= (long nOperand);
```

### <a name="parameters"></a>Параметры

*nOperand*<br/>
Делитель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объекта. Если делитель равен 0, возникнет ошибка assert.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#60](../../atl/codesnippet/cpp/ccomcurrency-class_8.cpp)]

##  <a name="operator_add"></a>  CComCurrency::operator +

Этот оператор используется для сложения объекта `CComCurrency`.

```
CComCurrency operator+(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*cur*<br/>
`CComCurrency` Объект для добавления к исходному объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CComCurrency` объект, представляющий результат сложения. В случае возникновения ошибки, например переполнение, этот оператор вызывает `AtlThrow` с HRESULT, описывающее ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#61](../../atl/codesnippet/cpp/ccomcurrency-class_9.cpp)]

##  <a name="operator_add_eq"></a>  CComCurrency::operator +=

Этот оператор используется для сложения объекта `CComCurrency` и назначения ему результата.

```
const CComCurrency& operator+= (const CComCurrency& cur);
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объекта. В случае возникновения ошибки, например переполнение, этот оператор вызывает `AtlThrow` с HRESULT, описывающее ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#62](../../atl/codesnippet/cpp/ccomcurrency-class_10.cpp)]

##  <a name="operator_lt"></a>  CComCurrency::operator &lt;

Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить меньший из них.

```
bool operator<(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект меньше второго, значение FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#63](../../atl/codesnippet/cpp/ccomcurrency-class_11.cpp)]

##  <a name="operator_lt_eq"></a>  CComCurrency::operator &lt;=

Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или меньший из них.

```
bool operator<= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект меньше или равно значению второго, FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#64](../../atl/codesnippet/cpp/ccomcurrency-class_12.cpp)]

##  <a name="operator_eq"></a>  CComCurrency::operator =

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
Объект `CComCurrency`.

*cySrc*<br/>
Переменная типа валюты.

*sSrc*, *fSrc*, *lSrc*, *bSrc*, *usSrc*, *dSrc*, *cSrc* , *ulSrc*, *dSrc*<br/>
Числовое значение, присваиваемое `CComCurrency` объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объекта. В случае возникновения ошибки, например переполнение, этот оператор вызывает `AtlThrow` с HRESULT, описывающее ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#65](../../atl/codesnippet/cpp/ccomcurrency-class_13.cpp)]

##  <a name="operator_-_eq"></a>  CComCurrency::operator-=

Этот оператор используется для вычитания объекта `CComCurrency` и назначения ему результата.

```
const CComCurrency& operator-= (const CComCurrency& cur);
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объекта. В случае возникновения ошибки, например переполнение, этот оператор вызывает `AtlThrow` с HRESULT, описывающее ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#66](../../atl/codesnippet/cpp/ccomcurrency-class_14.cpp)]

##  <a name="operator_eq_eq"></a>  CComCurrency::operator ==

Этот оператор сравнивает два объекта `CComCurrency` на равенство.

```
bool operator== (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*cur*<br/>
`CComCurrency` Объект для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если объекты равны (т. е `m_currency` данные-члены, как integer и дробную часть, в обоих объектов имеют одинаковое значение), и FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#67](../../atl/codesnippet/cpp/ccomcurrency-class_15.cpp)]

##  <a name="operator_gt"></a>  CComCurrency::operator &gt;

Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить больший из них.

```
bool operator>(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект больше второго, значение FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#68](../../atl/codesnippet/cpp/ccomcurrency-class_16.cpp)]

##  <a name="operator_gt_eq"></a>  CComCurrency::operator &gt;=

Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или больший из них.

```
bool operator>= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект больше или равен ему, значение FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#69](../../atl/codesnippet/cpp/ccomcurrency-class_17.cpp)]

##  <a name="operator_currency"></a>  CComCurrency::operator валюты

Эти операторы используются для приведения `CComCurrency` объект в тип данных валюты.

```
operator CURRENCY&() throw();
operator const CURRENCY&() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на объект валюты.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#70](../../atl/codesnippet/cpp/ccomcurrency-class_18.cpp)]

##  <a name="round"></a>  CComCurrency::Round

Вызовите этот метод для округления валют для указанного числа десятичных знаков.

```
HRESULT Roundint nDecimals);
```

### <a name="parameters"></a>Параметры

*nDecimals*<br/>
Количество цифр, к которому `m_currency` округляется, в диапазоне от 0 до 4.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#52](../../atl/codesnippet/cpp/ccomcurrency-class_19.cpp)]

##  <a name="setfraction"></a>  CComCurrency::SetFraction

Вызовите этот метод для установки дробной части объекта `CComCurrency`.

```
HRESULT SetFraction(SHORT nFraction);
```

### <a name="parameters"></a>Параметры

*nFraction*<br/>
Значение, присваиваемое дробная часть `m_currency` элемента данных. Знак дробная должно быть таким же, как компонент целое число, а значение должно быть в диапазоне от-(CY_MIN_FRACTION) на 9 (CY_MAX_FRACTION).

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#53](../../atl/codesnippet/cpp/ccomcurrency-class_20.cpp)]

##  <a name="setinteger"></a>  CComCurrency::SetInteger

Вызовите этот метод для установки целой части объекта `CComCurrency`.

```
HRESULT SetInteger(LONGLONG nInteger);
```

### <a name="parameters"></a>Параметры

*nInteger*<br/>
Значение, присваиваемое целой части `m_currency` элемент данных. Знак целой должно соответствовать знак существующий компонент долей.

*nInteger* должно находиться в диапазоне CY_MIN_INTEGER для CY_MAX_INTEGER включительно. Эти значения определены в файле atlcur.h.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#54](../../atl/codesnippet/cpp/ccomcurrency-class_21.cpp)]

## <a name="see-also"></a>См. также

[Класс COleCurrency](../../mfc/reference/colecurrency-class.md)<br/>
[ВАЛЮТА](/windows/desktop/api/wtypes/ns-wtypes-tagcy)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
