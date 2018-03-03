---
title: "Класс CComCurrency | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c3ef0cdc45d4f3b84c738e5eec24d76a1f9b7fe2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccomcurrency-class"></a>Класс CComCurrency
`CComCurrency` содержит методы и операторы для создания объекта CURRENCY и управления им.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComCurrency
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComCurrency::CComCurrency](#ccomcurrency)|Конструктор объекта `CComCurrency`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComCurrency::GetCurrencyPtr](#getcurrencyptr)|Возвращает адрес элемента данных `m_currency`.|  
|[CComCurrency::GetFraction](#getfraction)|Вызовите этот метод для возврата дробной части объекта `CComCurrency`.|  
|[CComCurrency::GetInteger](#getinteger)|Вызовите этот метод для возврата целой части объекта `CComCurrency`.|  
|[CComCurrency::Round](#round)|Вызовите этот метод для округления объекта `CComCurrency` до ближайшего целого значения.|  
|[CComCurrency::SetFraction](#setfraction)|Вызовите этот метод для установки дробной части объекта `CComCurrency`.|  
|[CComCurrency::SetInteger](#setinteger)|Вызовите этот метод для установки целой части объекта `CComCurrency`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
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
|[CComCurrency::operator ВАЛЮТ](#operator_currency)|Приведение объекта `CURRENCY`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComCurrency::m_currency](#m_currency)|Переменная `CURRENCY`, созданная экземпляром класса.|  
  
## <a name="remarks"></a>Примечания  
 `CComCurrency`является оболочкой для **валюты** тип данных. **ВАЛЮТА** реализуется как целое 8-байтное дополнительном умноженное на 10 000. Это позволяет получить число с фиксированной запятой с 15 разрядами слева от десятичной запятой и 4 разрядами справа от нее. **Валюты** тип данных чрезвычайно полезна для денежных расчетов или расчетов с фиксированной запятой, когда важна точность.  
  
 **CComCurrency** оболочки реализует арифметические операции присваивания и сравнения операции для этого типа с фиксированной запятой. Поддерживаемые приложения были выбраны для управления ошибками округления, которые могут возникнуть во время вычислений с фиксированной запятой.  
  
 Объект `CComCurrency` предоставляет доступ к числа с обеих сторон от десятичного разделителя в формате из двух компонентов: целого компонента со знаком, в котором хранится значение слева от десятичной запятой, и дробного компонента, в котором хранится значение справа от десятичной запятой. Дробная сохраняется как целое значение от — 9 999 ( **CY_MIN_FRACTION**) до + 9 999 ( **CY_MAX_FRACTION**). Метод [CComCurrency::GetFraction](#getfraction) возвращает значение, умноженное на 10 000 ( **CY_SCALE**).  
  
 При указании целого и дробного компонента объекта **CComCurrency** следует помнить, что дробная является числом в диапазоне от 0 до 9999. Это важно при работе с валютой, например долларом США, когда суммы выражаются с использованием только двух значащих цифр после запятой. Хотя две последние цифры не отображаются, их необходимо учитывать.  
  
|Значение|Возможные значения CComCurrency|  
|-----------|---------------------------------------|  
|$10.50|CComCurrency(10,5000) *или* CComCurrency(10.50)|  
|$10.05|CComCurrency(10,500) *или* CComCurrency(10.05)|  
  
 Значения **CY_MIN_FRACTION**, **CY_MAX_FRACTION**, и **CY_SCALE** определены в файле atlcur.h.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcur.h  
  
##  <a name="ccomcurrency"></a>CComCurrency::CComCurrency  
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
 `curSrc`  
 Существующий объект `CComCurrency`.  
  
 `cySrc`  
 Переменная типа **валюты**.  
  
 `bSrc`, `dSrc`, `fSrc`, `lSrc`, *sSrc*, *ulSrc usSrc*  
 Начальное значение, присвоенное переменной-члена `m_currency`.  
  
 `cSrc`  
 Символ, содержащий исходное значение, присвоенное переменной-члена `m_currency`.  
  
 `nInteger`, *nFraction*  
 Целое число со знаком и дробного компонента объекта начальной денежное значение. В разделе [CComCurrency](../../atl/reference/ccomcurrency-class.md) получения дополнительных сведений.  
  
 `pDispSrc`  
 `IDispatch` Указатель.  
  
 *varSrc*  
 Переменная типа **VARIANT**. Языковой стандарт текущего потока используется для выполнения преобразования.  
  
 `szSrc`  
 Строка Юникода или ANSI, содержащая начальное значение. Языковой стандарт текущего потока используется для выполнения преобразования.  
  
### <a name="remarks"></a>Примечания  
 Конструктор задает начальное значение [CComCurrency::m_currency](#m_currency)и принимает самые разнообразные типы данных, включая целые числа, строки, числа с плавающей запятой, **валюты** переменные и другие `CComCurrency` объектов. Если значение не указано, `m_currency` имеет значение 0.  
  
 В случае ошибки, например переполнение, конструкторы, отсутствием пустую спецификацию исключений ( **throw()**) вызовите `AtlThrow` с результатом HRESULT, описывающее ошибку.  
  
 При использовании значений с плавающей запятой или double для присвоения значения, обратите внимание, что **CComCurrency(10.50)** эквивалентно **CComCurrency(10,5000)** и не **CComCurrency(10,50)**.  
  
##  <a name="getcurrencyptr"></a>CComCurrency::GetCurrencyPtr  
 Возвращает адрес элемента данных `m_currency`.  
  
```
CURRENCY* GetCurrencyPtr() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает адрес `m_currency` элемент данных  
  
##  <a name="getfraction"></a>CComCurrency::GetFraction  
 Вызовите этот метод для возврата дробной части `CComCurrency` объекта.  
  
```
SHORT GetFraction() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дробная часть `m_currency` элемента данных.  
  
### <a name="remarks"></a>Примечания  
 Дробная часть — 4-значное целое значение от — 9 999 ( **CY_MIN_FRACTION**) до + 9 999 ( **CY_MAX_FRACTION**). `GetFraction`Возвращает это значение, умноженного на 10000 ( **CY_SCALE**). Значения **CY_MIN_FRACTION**, **CY_MAX_FRACTION**, и **CY_SCALE** определены в файле atlcur.h.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#50](../../atl/codesnippet/cpp/ccomcurrency-class_1.cpp)]  
  
##  <a name="getinteger"></a>CComCurrency::GetInteger  
 Этот метод вызывается для получения целой части `CComCurrency` объекта.  
  
```
LONGLONG GetInteger() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает целочисленный `m_currency` члена данных.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#51](../../atl/codesnippet/cpp/ccomcurrency-class_2.cpp)]  
  
##  <a name="m_currency"></a>CComCurrency::m_currency  
 **Валюты** члена данных.  
  
```
CURRENCY m_currency;
```  
  
### <a name="remarks"></a>Примечания  
 Этот член содержит валюты доступ и управление им с помощью методов этого класса.  
  
##  <a name="operator_-"></a>CComCurrency::operator-  
 Этот оператор используется для вычитания объекта `CComCurrency`.  
  
```
CComCurrency operator-() const;
CComCurrency operator-(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 Объект `CComCurrency`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CComCurrency` объект, представляющий результат вычитания. В случае ошибки, например переполнение, этот оператор вызывает `AtlThrow` с результатом HRESULT, описывающее ошибку.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#55](../../atl/codesnippet/cpp/ccomcurrency-class_3.cpp)]  
  
##  <a name="operator_neq"></a>CComCurrency::operator! =  
 Этот оператор сравнивает два объекта на неравенство.  
  
```
bool operator!= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 Сравниваемый объект `CComCurrency`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если сравниваемые элемента не равно `CComCurrency` объекта; в противном случае **false**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#56](../../atl/codesnippet/cpp/ccomcurrency-class_4.cpp)]  
  
##  <a name="operator_star"></a>CComCurrency::operator *  
 Этот оператор используется для умножения объекта `CComCurrency`.  
  
```
CComCurrency operator*(long nOperand) const;
CComCurrency operator*(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Параметры  
 `nOperand`  
 Множитель.  
  
 `cur`  
 `CComCurrency` Объекта, используемое как множитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CComCurrency` объект, представляющий результат умножения. В случае ошибки, например переполнение, этот оператор вызывает `AtlThrow` с результатом HRESULT, описывающее ошибку.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#57](../../atl/codesnippet/cpp/ccomcurrency-class_5.cpp)]  
  
##  <a name="operator_star_eq"></a>CComCurrency::operator * =  
 Этот оператор используется для умножения объекта `CComCurrency` и назначения ему результата.  
  
```
const CComCurrency& operator*= (long nOperand);
const CComCurrency& operator*= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>Параметры  
 `nOperand`  
 Множитель.  
  
 `cur`  
 `CComCurrency` Объекта, используемое как множитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CComCurrency` объекта. В случае ошибки, например переполнение, этот оператор вызывает `AtlThrow` с результатом HRESULT, описывающее ошибку.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#58](../../atl/codesnippet/cpp/ccomcurrency-class_6.cpp)]  
  
##  <a name="operator_div"></a>CComCurrency::operator /  
 Этот оператор используется для деления объекта `CComCurrency`.  
  
```
CComCurrency operator/(long nOperand) const;
```  
  
### <a name="parameters"></a>Параметры  
 `nOperand`  
 Делитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CComCurrency` объект, представляющий результат деления. Если делитель равен 0, произойдет сбой утверждения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#59](../../atl/codesnippet/cpp/ccomcurrency-class_7.cpp)]  
  
##  <a name="operator_div_eq"></a>CComCurrency::operator / =  
 Этот оператор используется для деления объекта `CComCurrency` и назначения ему результата.  
  
```
const CComCurrency& operator/= (long nOperand);
```  
  
### <a name="parameters"></a>Параметры  
 `nOperand`  
 Делитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CComCurrency` объекта. Если делитель равен 0, произойдет сбой утверждения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#60](../../atl/codesnippet/cpp/ccomcurrency-class_8.cpp)]  
  
##  <a name="operator_add"></a>CComCurrency::operator +  
 Этот оператор используется для сложения объекта `CComCurrency`.  
  
```
CComCurrency operator+(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 `CComCurrency` Объект для добавления к исходному объекту.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CComCurrency` объект, представляющий результат сложения. В случае ошибки, например переполнение, этот оператор вызывает `AtlThrow` с результатом HRESULT, описывающее ошибку.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#61](../../atl/codesnippet/cpp/ccomcurrency-class_9.cpp)]  
  
##  <a name="operator_add_eq"></a>CComCurrency::operator +=  
 Этот оператор используется для сложения объекта `CComCurrency` и назначения ему результата.  
  
```
const CComCurrency& operator+= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 Объект `CComCurrency`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CComCurrency` объекта. В случае ошибки, например переполнение, этот оператор вызывает `AtlThrow` с результатом HRESULT, описывающее ошибку.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#62](../../atl/codesnippet/cpp/ccomcurrency-class_10.cpp)]  
  
##  <a name="operator_lt"></a>CComCurrency::operator&lt;  
 Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить меньший из них.  
  
```
bool operator<(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 Объект `CComCurrency`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект меньше, чем значение второго **false** в противном случае.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#63](../../atl/codesnippet/cpp/ccomcurrency-class_11.cpp)]  
  
##  <a name="operator_lt_eq"></a>CComCurrency::operator&lt;=  
 Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или меньший из них.  
  
```
bool operator<= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 Объект `CComCurrency`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект меньше или равен второму, **false** в противном случае.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#64](../../atl/codesnippet/cpp/ccomcurrency-class_12.cpp)]  
  
##  <a name="operator_eq"></a>CComCurrency::operator =  
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
 `curSrc`  
 Объект **CComCurrency** объекта.  
  
 `cySrc`  
 Переменная типа **валюты**.  
  
 *sSrc*, `fSrc`, `lSrc`, *bSrc*, *usSrc*, `dSrc`, *cSrc*, *ulSrc*,`dSrc`  
 Числовое значение, присваиваемое `CComCurrency` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CComCurrency` объекта. В случае ошибки, например переполнение, этот оператор вызывает `AtlThrow` с результатом HRESULT, описывающее ошибку.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#65](../../atl/codesnippet/cpp/ccomcurrency-class_13.cpp)]  
  
##  <a name="operator_-_eq"></a>CComCurrency::operator-=  
 Этот оператор используется для вычитания объекта `CComCurrency` и назначения ему результата.  
  
```
const CComCurrency& operator-= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 Объект `CComCurrency`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CComCurrency` объекта. В случае ошибки, например переполнение, этот оператор вызывает `AtlThrow` с результатом HRESULT, описывающее ошибку.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#66](../../atl/codesnippet/cpp/ccomcurrency-class_14.cpp)]  
  
##  <a name="operator_eq_eq"></a>CComCurrency::operator ==  
 Этот оператор сравнивает два объекта `CComCurrency` на равенство.  
  
```
bool operator== (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 `CComCurrency` Объект для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если объекты равны (т. е `m_currency` элементы данных, как целое число и дробную часть, в обоих объектов имеют одинаковое значение), **false** в противном случае.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#67](../../atl/codesnippet/cpp/ccomcurrency-class_15.cpp)]  
  
##  <a name="operator_gt"></a>CComCurrency::operator&gt;  
 Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить больший из них.  
  
```
bool operator>(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 Объект `CComCurrency`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект больше второго, **false** в противном случае.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#68](../../atl/codesnippet/cpp/ccomcurrency-class_16.cpp)]  
  
##  <a name="operator_gt_eq"></a>CComCurrency::operator&gt;=  
 Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или больший из них.  
  
```
bool operator>= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 Объект `CComCurrency`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект больше или равен ему, **false** в противном случае.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#69](../../atl/codesnippet/cpp/ccomcurrency-class_17.cpp)]  
  
##  <a name="operator_currency"></a>CComCurrency::operator ВАЛЮТ  
 Эти операторы используются для приведения `CComCurrency` объект **валюты** тип данных.  
  
```  
operator CURRENCY&() throw();
operator const CURRENCY&() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на **валюты** объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#70](../../atl/codesnippet/cpp/ccomcurrency-class_18.cpp)]  
  
##  <a name="round"></a>CComCurrency::Round  
 Вызовите этот метод для округления валюты указанного количества десятичных разрядов.  
  
```
HRESULT Roundint nDecimals);
```  
  
### <a name="parameters"></a>Параметры  
 *nDecimals*  
 Количество цифр, к которому `m_currency` будет округляться в диапазоне от 0 до 4.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#52](../../atl/codesnippet/cpp/ccomcurrency-class_19.cpp)]  
  
##  <a name="setfraction"></a>CComCurrency::SetFraction  
 Вызовите этот метод для установки дробной части объекта `CComCurrency`.  
  
```
HRESULT SetFraction(SHORT nFraction);
```  
  
### <a name="parameters"></a>Параметры  
 *nFraction*  
 Значение, присваиваемое дробная часть `m_currency` элемента данных. Знак дробная должно быть таким же, как компонент целое число со знаком, а значение должно быть в диапазоне от-( **CY_MIN_FRACTION**) для + 9 999 ( **CY_MAX_FRACTION**).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#53](../../atl/codesnippet/cpp/ccomcurrency-class_20.cpp)]  
  
##  <a name="setinteger"></a>CComCurrency::SetInteger  
 Вызовите этот метод для установки целой части объекта `CComCurrency`.  
  
```
HRESULT SetInteger(LONGLONG nInteger);
```  
  
### <a name="parameters"></a>Параметры  
 `nInteger`  
 Значение, присваиваемое целой части `m_currency` члена данных. Знак целочисленный должно соответствовать знак существующих дробного компонента.  
  
 `nInteger`должно быть в диапазоне **CY_MIN_INTEGER** для **CY_MAX_INTEGER** включительно. Эти значения определены в файле atlcur.h.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#54](../../atl/codesnippet/cpp/ccomcurrency-class_21.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс COleCurrency](../../mfc/reference/colecurrency-class.md)   
 [ВАЛЮТА](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
