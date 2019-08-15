---
title: Класс Ккомкурренци
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
ms.openlocfilehash: 11463b7113876abdf0743b9f8c7df373fadd99ef
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497294"
---
# <a name="ccomcurrency-class"></a>Класс Ккомкурренци

`CComCurrency` содержит методы и операторы для создания объекта CURRENCY и управления им.

## <a name="syntax"></a>Синтаксис

```
class CComCurrency
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Ккомкурренци:: Ккомкурренци](#ccomcurrency)|Конструктор объекта `CComCurrency`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Ккомкурренци:: Жеткурренциптр](#getcurrencyptr)|Возвращает адрес элемента данных `m_currency`.|
|[Ккомкурренци:: дробь](#getfraction)|Вызовите этот метод для возврата дробной части объекта `CComCurrency`.|
|[Ккомкурренци:: integer](#getinteger)|Вызовите этот метод для возврата целой части объекта `CComCurrency`.|
|[Ккомкурренци:: Round](#round)|Вызовите этот метод для округления объекта `CComCurrency` до ближайшего целого значения.|
|[Ккомкурренци:: Сетфрактион](#setfraction)|Вызовите этот метод для установки дробной части объекта `CComCurrency`.|
|[Ккомкурренци:: Сетинтежер](#setinteger)|Вызовите этот метод для установки целой части объекта `CComCurrency`.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[Ккомкурренци:: operator —](#operator_-)|Этот оператор используется для вычитания объекта `CComCurrency`.|
|[Ккомкурренци:: operator! =](#operator_neq)|Проверяет неравенство двух объектов `CComCurrency`.|
|[Ккомкурренци:: operator *](#operator_star)|Этот оператор используется для умножения объекта `CComCurrency`.|
|[Ккомкурренци:: operator * =](#operator_star_eq)|Этот оператор используется для умножения объекта `CComCurrency` и назначения ему результата.|
|[Ккомкурренци:: operator/](#operator_div)|Этот оператор используется для деления объекта `CComCurrency`.|
|[Ккомкурренци:: operator/=](#operator_div_eq)|Этот оператор используется для деления объекта `CComCurrency` и назначения ему результата.|
|[Ккомкурренци:: operator +](#operator_add)|Этот оператор используется для сложения объекта `CComCurrency`.|
|[Ккомкурренци:: operator + =](#operator_add_eq)|Этот оператор используется для сложения объекта `CComCurrency` и назначения ему результата.|
|[Ккомкурренци:: operator <](#operator_lt)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить меньший из них.|
|[Ккомкурренци:: operator < =](#operator_lt_eq)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или меньший из них.|
|[Ккомкурренци:: operator =](#operator_eq)|Этот оператор присваивает объекту `CComCurrency` новое значение.|
|[Ккомкурренци:: operator-=](#operator_-_eq)|Этот оператор используется для вычитания объекта `CComCurrency` и назначения ему результата.|
|[Ккомкурренци:: operator = =](#operator_eq_eq)|Этот оператор сравнивает два объекта `CComCurrency` на равенство.|
|[Ккомкурренци:: operator >](#operator_gt)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить больший из них.|
|[Ккомкурренци:: operator > =](#operator_gt_eq)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или больший из них.|
|[Ккомкурренци:: оператор CURRENCY](#operator_currency)|Приводит объект CURRENCY.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Ккомкурренци:: m_currency](#m_currency)|Переменная CURRENCY, созданная экземпляром класса.|

## <a name="remarks"></a>Примечания

`CComCurrency`— Это оболочка для типа данных CURRENCY. Валюта реализуется как 8-байтовое целое число, которое масштабируется по 10 000. Это позволяет получить число с фиксированной запятой с 15 разрядами слева от десятичной запятой и 4 разрядами справа от нее. Тип данных CURRENCY чрезвычайно удобен для вычислений, связанных с деньгами, или для любых вычислений с фиксированной запятой, где важна точность.

`CComCurrency` Обертка реализует операции арифметического, присваивания и сравнения для этого типа с фиксированной запятой. Поддерживаемые приложения были выбраны для управления ошибками округления, которые могут возникнуть во время вычислений с фиксированной запятой.

Объект `CComCurrency` предоставляет доступ к числа с обеих сторон от десятичного разделителя в формате из двух компонентов: целого компонента со знаком, в котором хранится значение слева от десятичной запятой, и дробного компонента, в котором хранится значение справа от десятичной запятой. Дробный компонент хранится внутренне как целочисленное значение от-9999 (CY_MIN_FRACTION) до + 9999 (CY_MAX_FRACTION). Метод [ккомкурренци::-дробь](#getfraction) возвращает значение, масштабированное с коэффициентом 10000 (CY_SCALE).

При указании целочисленных и дробных компонентов `CComCurrency` объекта Помните, что дробный компонент является числом в диапазоне от 0 до 9999. Это важно при работе с валютой, например долларом США, когда суммы выражаются с использованием только двух значащих цифр после запятой. Хотя две последние цифры не отображаются, их необходимо учитывать.

|Значение|Возможные значения CComCurrency|
|-----------|---------------------------------------|
|$10.50|Ккомкурренци (10, 5000) *или* ккомкурренци (10.50)|
|$10.05|Ккомкурренци (10500) *или* ккомкурренци (10.05)|

Значения CY_MIN_FRACTION, CY_MAX_FRACTION и CY_SCALE определены в атлкур. h.

## <a name="requirements"></a>Требования

**Заголовок:** атлкур. h

##  <a name="ccomcurrency"></a>Ккомкурренци:: Ккомкурренци

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

*курсрк*<br/>
Существующий объект `CComCurrency`.

*цисрк*<br/>
Переменная типа CURRENCY.

*бсрк*, *дсрк*, *ФСРК*, *лсрк*, *ССРК*, *улсрк, уссрк*<br/>
Начальное значение, присваиваемое переменной `m_currency`члена.

*ксрк*<br/>
Символ, содержащий начальное значение, присвоенное переменной `m_currency`-члену.

*нинтежер*, *нфрактион*<br/>
Целочисленные и дробные компоненты начального денежного значения. Дополнительные сведения см. в обзоре [ккомкурренци](../../atl/reference/ccomcurrency-class.md) .

*пдиспсрк*<br/>
`IDispatch` Указатель.

*варсрк*<br/>
Переменная типа VARIANT. Языковой стандарт текущего потока используется для выполнения преобразования.

*сзсрк*<br/>
Строка в Юникоде или ANSI, содержащая начальное значение. Языковой стандарт текущего потока используется для выполнения преобразования.

### <a name="remarks"></a>Примечания

Конструктор задает начальное значение [ккомкурренци:: m_currency](#m_currency)и принимает широкий спектр типов данных, включая целые числа, строки, числа с плавающей запятой, переменные валюты и другие `CComCurrency` объекты. Если значение не указано, `m_currency` присваивается значение 0.

В случае ошибки, например переполнения, конструкторы не имеют пустого вызова `AtlThrow` спецификации исключения (**Throw ()** ) со значением HRESULT, описывающим ошибку.

При использовании значений с плавающей запятой или двойной точности для присваивания значения Обратите внимание, `CComCurrency(10,5000)` что `CComCurrency(10.50)` эквивалентно и Not `CComCurrency(10,50)`.

##  <a name="getcurrencyptr"></a>Ккомкурренци:: Жеткурренциптр

Возвращает адрес элемента данных `m_currency`.

```
CURRENCY* GetCurrencyPtr() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает адрес `m_currency` элемента данных

##  <a name="getfraction"></a>Ккомкурренци:: дробь

Вызовите этот метод, чтобы вернуть дробный компонент `CComCurrency` объекта.

```
SHORT GetFraction() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает дробный компонент `m_currency` элемента данных.

### <a name="remarks"></a>Примечания

Дробный компонент — это 4-значное целочисленное значение от-9999 (CY_MIN_FRACTION) до + 9999 (CY_MAX_FRACTION). `GetFraction`Возвращает это значение, масштабированное на 10000 (CY_SCALE). Значения CY_MIN_FRACTION, CY_MAX_FRACTION и CY_SCALE определены в атлкур. h.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#50](../../atl/codesnippet/cpp/ccomcurrency-class_1.cpp)]

##  <a name="getinteger"></a>Ккомкурренци:: integer

Вызовите этот метод, чтобы получить целочисленный компонент `CComCurrency` объекта.

```
LONGLONG GetInteger() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает целочисленный компонент `m_currency` элемента данных.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#51](../../atl/codesnippet/cpp/ccomcurrency-class_2.cpp)]

##  <a name="m_currency"></a>Ккомкурренци:: m_currency

Элемент данных валюты.

```
CURRENCY m_currency;
```

### <a name="remarks"></a>Примечания

Этот элемент содержит валюту, к которой обращаются и которыми манипулируют методы этого класса.

##  <a name="operator_-"></a>Ккомкурренци:: operator —

Этот оператор используется для вычитания объекта `CComCurrency`.

```
CComCurrency operator-() const;
CComCurrency operator-(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

`CComCurrency` Возвращает объект, представляющий результат вычитания. В случае ошибки, например переполнения, этот оператор вызывает `AtlThrow` с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#55](../../atl/codesnippet/cpp/ccomcurrency-class_3.cpp)]

##  <a name="operator_neq"></a>Ккомкурренци:: operator! =

Этот оператор сравнивает два объекта на неравенство.

```
bool operator!= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Сравниваемый объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если сравниваемый элемент не равен `CComCurrency` объекту; в противном случае — значение false.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#56](../../atl/codesnippet/cpp/ccomcurrency-class_4.cpp)]

##  <a name="operator_star"></a>Ккомкурренци:: operator *

Этот оператор используется для умножения объекта `CComCurrency`.

```
CComCurrency operator*(long nOperand) const;
CComCurrency operator*(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*ноперанд*<br/>
Множитель.

*cur*<br/>
`CComCurrency` Объект, используемый в качестве множителя.

### <a name="return-value"></a>Возвращаемое значение

`CComCurrency` Возвращает объект, представляющий результат умножения. В случае ошибки, например переполнения, этот оператор вызывает `AtlThrow` с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#57](../../atl/codesnippet/cpp/ccomcurrency-class_5.cpp)]

##  <a name="operator_star_eq"></a>Ккомкурренци:: operator\*=

Этот оператор используется для умножения объекта `CComCurrency` и назначения ему результата.

```
const CComCurrency& operator*= (long nOperand);
const CComCurrency& operator*= (const CComCurrency& cur);
```

### <a name="parameters"></a>Параметры

*ноперанд*<br/>
Множитель.

*cur*<br/>
`CComCurrency` Объект, используемый в качестве множителя.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объект. В случае ошибки, например переполнения, этот оператор вызывает `AtlThrow` с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#58](../../atl/codesnippet/cpp/ccomcurrency-class_6.cpp)]

##  <a name="operator_div"></a>Ккомкурренци:: operator/

Этот оператор используется для деления объекта `CComCurrency`.

```
CComCurrency operator/(long nOperand) const;
```

### <a name="parameters"></a>Параметры

*ноперанд*<br/>
Делитель.

### <a name="return-value"></a>Возвращаемое значение

`CComCurrency` Возвращает объект, представляющий результат деления. Если делитель равен 0, произойдет сбой Assert.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#59](../../atl/codesnippet/cpp/ccomcurrency-class_7.cpp)]

##  <a name="operator_div_eq"></a>Ккомкурренци:: operator/=

Этот оператор используется для деления объекта `CComCurrency` и назначения ему результата.

```
const CComCurrency& operator/= (long nOperand);
```

### <a name="parameters"></a>Параметры

*ноперанд*<br/>
Делитель.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объект. Если делитель равен 0, произойдет сбой Assert.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#60](../../atl/codesnippet/cpp/ccomcurrency-class_8.cpp)]

##  <a name="operator_add"></a>Ккомкурренци:: operator +

Этот оператор используется для сложения объекта `CComCurrency`.

```
CComCurrency operator+(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*cur*<br/>
`CComCurrency` Объект, добавляемый в исходный объект.

### <a name="return-value"></a>Возвращаемое значение

`CComCurrency` Возвращает объект, представляющий результат сложения. В случае ошибки, например переполнения, этот оператор вызывает `AtlThrow` с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#61](../../atl/codesnippet/cpp/ccomcurrency-class_9.cpp)]

##  <a name="operator_add_eq"></a>Ккомкурренци:: operator + =

Этот оператор используется для сложения объекта `CComCurrency` и назначения ему результата.

```
const CComCurrency& operator+= (const CComCurrency& cur);
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объект. В случае ошибки, например переполнения, этот оператор вызывает `AtlThrow` с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#62](../../atl/codesnippet/cpp/ccomcurrency-class_10.cpp)]

##  <a name="operator_lt"></a>Ккомкурренци:: operator&lt;

Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить меньший из них.

```
bool operator<(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект меньше второго, и FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#63](../../atl/codesnippet/cpp/ccomcurrency-class_11.cpp)]

##  <a name="operator_lt_eq"></a>Ккомкурренци:: operator&lt;=

Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или меньший из них.

```
bool operator<= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект меньше или равен второму, и FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#64](../../atl/codesnippet/cpp/ccomcurrency-class_12.cpp)]

##  <a name="operator_eq"></a>Ккомкурренци:: operator =

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

*курсрк*<br/>
Объект `CComCurrency`.

*цисрк*<br/>
Переменная типа CURRENCY.

*ССРК*, *ФСРК*, *лсрк*, *бсрк*, *уссрк*, *дсрк*, *КСРК*, *улсрк*, *дсрк*<br/>
Числовое значение, присваиваемое `CComCurrency` объекту.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объект. В случае ошибки, например переполнения, этот оператор вызывает `AtlThrow` с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#65](../../atl/codesnippet/cpp/ccomcurrency-class_13.cpp)]

##  <a name="operator_-_eq"></a>Ккомкурренци:: operator-=

Этот оператор используется для вычитания объекта `CComCurrency` и назначения ему результата.

```
const CComCurrency& operator-= (const CComCurrency& cur);
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CComCurrency` объект. В случае ошибки, например переполнения, этот оператор вызывает `AtlThrow` с помощью HRESULT, описывающего ошибку.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#66](../../atl/codesnippet/cpp/ccomcurrency-class_14.cpp)]

##  <a name="operator_eq_eq"></a>Ккомкурренци:: operator = =

Этот оператор сравнивает два объекта `CComCurrency` на равенство.

```
bool operator== (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Сравниваемый `CComCurrency` объект.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если объекты равны (то есть `m_currency` элементы данных, как целые, так и дробные, в обоих объектах имеют одинаковое значение), в противном случае — значение false.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#67](../../atl/codesnippet/cpp/ccomcurrency-class_15.cpp)]

##  <a name="operator_gt"></a>Ккомкурренци:: operator&gt;

Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить больший из них.

```
bool operator>(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект больше второго, и FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#68](../../atl/codesnippet/cpp/ccomcurrency-class_16.cpp)]

##  <a name="operator_gt_eq"></a>Ккомкурренци:: operator&gt;=

Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или больший из них.

```
bool operator>= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Параметры

*cur*<br/>
Объект `CComCurrency`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если первый объект больше или равен второму, и FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#69](../../atl/codesnippet/cpp/ccomcurrency-class_17.cpp)]

##  <a name="operator_currency"></a>Ккомкурренци:: оператор CURRENCY

Эти операторы используются для приведения `CComCurrency` объекта к типу данных Currency.

```
operator CURRENCY&() throw();
operator const CURRENCY&() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на объект CURRENCY.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#70](../../atl/codesnippet/cpp/ccomcurrency-class_18.cpp)]

##  <a name="round"></a>Ккомкурренци:: Round

Вызовите этот метод, чтобы округлить валюту до указанного числа десятичных разрядов.

```
HRESULT Roundint nDecimals);
```

### <a name="parameters"></a>Параметры

*ндеЦималс*<br/>
Число знаков, до которого `m_currency` будет округляться значение в диапазоне от 0 до 4.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#52](../../atl/codesnippet/cpp/ccomcurrency-class_19.cpp)]

##  <a name="setfraction"></a>Ккомкурренци:: Сетфрактион

Вызовите этот метод для установки дробной части объекта `CComCurrency`.

```
HRESULT SetFraction(SHORT nFraction);
```

### <a name="parameters"></a>Параметры

*нфрактион*<br/>
Значение, присваиваемое дробному компоненту `m_currency` элемента данных. Знак дробного компонента должен быть таким же, как и целочисленный компонент, а значение должно находиться в диапазоне от-9999 (CY_MIN_FRACTION) до + 9999 (CY_MAX_FRACTION).

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#53](../../atl/codesnippet/cpp/ccomcurrency-class_20.cpp)]

##  <a name="setinteger"></a>Ккомкурренци:: Сетинтежер

Вызовите этот метод для установки целой части объекта `CComCurrency`.

```
HRESULT SetInteger(LONGLONG nInteger);
```

### <a name="parameters"></a>Параметры

*нинтежер*<br/>
Значение, присваиваемое целочисленному компоненту `m_currency` элемента данных. Знак целочисленного компонента должен соответствовать знаку существующего дробного компонента.

*нинтежер* должен находиться в диапазоне от CY_MIN_INTEGER до CY_MAX_INTEGER включительно. Эти значения определены в атлкур. h.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#54](../../atl/codesnippet/cpp/ccomcurrency-class_21.cpp)]

## <a name="see-also"></a>См. также

[Класс COleCurrency](../../mfc/reference/colecurrency-class.md)<br/>
[РЕЖИМЕ](/windows/win32/api/wtypes/ns-wtypes-cy)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
