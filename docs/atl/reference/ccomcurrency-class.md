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
caps.latest.revision: 21
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 1b0b4fa5f42bd060b08ef90d09eee8d9d2d76fe6
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcurrency-class"></a>Класс CComCurrency
`CComCurrency` содержит методы и операторы для создания объекта CURRENCY и управления им.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComCurrency
```  
  
## <a name="members"></a>Члены  
  
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
|[CComCurrency::operator или](#operator_div)|Этот оператор используется для деления объекта `CComCurrency`.|  
|[CComCurrency::operator / =](#operator_div_eq)|Этот оператор используется для деления объекта `CComCurrency` и назначения ему результата.|  
|[CComCurrency::operator +](#operator_add)|Этот оператор используется для сложения объекта `CComCurrency`.|  
|[CComCurrency::operator +=](#operator_add_eq)|Этот оператор используется для сложения объекта `CComCurrency` и назначения ему результата.|  
|[CComCurrency::operator](#operator_lt)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить меньший из них.|  
|[CComCurrency::operator<>](#operator_lt_eq)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или меньший из них.|  
|[CComCurrency::operator =](#operator_eq)|Этот оператор присваивает объекту `CComCurrency` новое значение.|  
|[CComCurrency::operator-=](#operator_-_eq)|Этот оператор используется для вычитания объекта `CComCurrency` и назначения ему результата.|  
|[CComCurrency::operator ==](#operator_eq_eq)|Этот оператор сравнивает два объекта `CComCurrency` на равенство.|  
|[CComCurrency::operator настроек](#operator_gt)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить больший из них.|  
|[CComCurrency::operator настроек =](#operator_gt_eq)|Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или больший из них.|  
|[CComCurrency::operator ВАЛЮТ](#operator_currency)|Приведение объекта `CURRENCY`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComCurrency::m_currency](#m_currency)|Переменная `CURRENCY`, созданная экземпляром класса.|  
  
## <a name="remarks"></a>Примечания  
 `CComCurrency`Представляет оболочку для **валюты** тип данных. **ВАЛЮТА** реализуется как целое значение 8-байтовое дополнительном масштабирования с 10 000. Это позволяет получить число с фиксированной запятой с 15 разрядами слева от десятичной запятой и 4 разрядами справа от нее. **Валюты** тип данных очень полезным для расчетов денежных или расчетов с фиксированной запятой, когда важна точность.  
  
 **CComCurrency** оболочки операциями, арифметические операторы, присваивания и сравнения для этого типа с фиксированной запятой. Поддерживаемые приложения были выбраны для управления ошибками округления, которые могут возникнуть во время вычислений с фиксированной запятой.  
  
 Объект `CComCurrency` предоставляет доступ к числа с обеих сторон от десятичного разделителя в формате из двух компонентов: целого компонента со знаком, в котором хранится значение слева от десятичной запятой, и дробного компонента, в котором хранится значение справа от десятичной запятой. Дробная сохраняется в виде целочисленного значения между-9999 ( **CY_MIN_FRACTION**) и +9999 ( **CY_MAX_FRACTION**). Метод [CComCurrency::GetFraction](#getfraction) возвращает значение масштабируется с коэффициентом 10000 ( **CY_SCALE**).  
  
 При задании integer и дробных компонентов из **CComCurrency** объекта, помните, что дробная является числом в диапазоне от 0 до 9999. Это важно при работе с валютой, например долларом США, когда суммы выражаются с использованием только двух значащих цифр после запятой. Хотя две последние цифры не отображаются, их необходимо учитывать.  
  
|Значение|Возможные значения CComCurrency|  
|-----------|---------------------------------------|  
|$10.50|CComCurrency(10,5000) *или* CComCurrency(10.50)|  
|$10.05|CComCurrency(10,500) *или* CComCurrency(10.05)|  
  
 Значения **CY_MIN_FRACTION**, **CY_MAX_FRACTION**, и **CY_SCALE** определены в atlcur.h.  
  
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
  
 `bSrc`, `dSrc`, `fSrc`, `lSrc`, *sSrc*, *ulSrc, usSrc*  
 Начальное значение, присваиваемое переменной-члена `m_currency`.  
  
 `cSrc`  
 Символ, содержащий начальное значение, присваиваемое переменной-члена `m_currency`.  
  
 `nInteger`, *nFraction*  
 Целое число со знаком и дробных компонентов начальной денежное значение. В разделе [CComCurrency](../../atl/reference/ccomcurrency-class.md) получения дополнительных сведений.  
  
 `pDispSrc`  
 `IDispatch` Указатель.  
  
 *varSrc*  
 Переменная типа **VARIANT**. Языковой стандарт текущего потока используется для выполнения преобразования.  
  
 `szSrc`  
 Строка Юникода или ANSI, содержащая начальное значение. Языковой стандарт текущего потока используется для выполнения преобразования.  
  
### <a name="remarks"></a>Примечания  
 Конструктор задает начальное значение [CComCurrency::m_currency](#m_currency)и принимает самые разнообразные типы данных, включая целые числа, строки, числа с плавающей запятой, **валюты** переменных и другие `CComCurrency` объекты. Если значение не указано, `m_currency` имеет значение 0.  
  
 В случае возникновения ошибки, например переполнение, конструкторы, отсутствие пустую спецификацию исключений ( **throw()**) вызвать `AtlThrow` с описанием ошибки HRESULT.  
  
 При использовании значений с плавающей запятой или double для присвоения значения, обратите внимание, что **CComCurrency(10.50)** эквивалентно **CComCurrency(10,5000)** и не **CComCurrency(10,50)**.  
  
##  <a name="getcurrencyptr"></a>CComCurrency::GetCurrencyPtr  
 Возвращает адрес элемента данных `m_currency`.  
  
```
CURRENCY* GetCurrencyPtr() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает адрес `m_currency` элемент данных  
  
##  <a name="getfraction"></a>CComCurrency::GetFraction  
 Вызовите этот метод для возврата дробная часть `CComCurrency` объекта.  
  
```
SHORT GetFraction() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дробная часть `m_currency` элемента данных.  
  
### <a name="remarks"></a>Примечания  
 Дробная представляет собой 4-значное целое значение от-9999 ( **CY_MIN_FRACTION**) и +9999 ( **CY_MAX_FRACTION**). `GetFraction`Возвращает это значение, умноженного на 10000 ( **CY_SCALE**). Значения **CY_MIN_FRACTION**, **CY_MAX_FRACTION**, и **CY_SCALE** определены в atlcur.h.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#50;](../../atl/codesnippet/cpp/ccomcurrency-class_1.cpp)]  
  
##  <a name="getinteger"></a>CComCurrency::GetInteger  
 Этот метод вызывается для получения целочисленный `CComCurrency` объекта.  
  
```
LONGLONG GetInteger() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает целочисленный `m_currency` члена данных.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#51;](../../atl/codesnippet/cpp/ccomcurrency-class_2.cpp)]  
  
##  <a name="m_currency"></a>CComCurrency::m_currency  
 **Валюты** члена данных.  
  
```
CURRENCY m_currency;
```  
  
### <a name="remarks"></a>Примечания  
 Этот член содержит валюты доступ и управлять с помощью методов этого класса.  
  
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
 Возвращает `CComCurrency` объект, представляющий результат вычитания. В случае возникновения ошибки, например переполнение, вызывает этот оператор `AtlThrow` с описанием ошибки HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#55;](../../atl/codesnippet/cpp/ccomcurrency-class_3.cpp)]  
  
##  <a name="operator_neq"></a>CComCurrency::operator! =  
 Этот оператор сравнивает два объекта на неравенство.  
  
```
bool operator!= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 Сравниваемый объект `CComCurrency`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если сравниваемые элемента не равен `CComCurrency` объекта; в противном случае — **false**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#56;](../../atl/codesnippet/cpp/ccomcurrency-class_4.cpp)]  
  
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
 `CComCurrency` Объект, используемый как множитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CComCurrency` объект, представляющий результат умножения. В случае возникновения ошибки, например переполнение, вызывает этот оператор `AtlThrow` с описанием ошибки HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#57;](../../atl/codesnippet/cpp/ccomcurrency-class_5.cpp)]  
  
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
 `CComCurrency` Объект, используемый как множитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CComCurrency` объекта. В случае возникновения ошибки, например переполнение, вызывает этот оператор `AtlThrow` с описанием ошибки HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#58;](../../atl/codesnippet/cpp/ccomcurrency-class_6.cpp)]  
  
##  <a name="operator_div"></a>CComCurrency::operator или  
 Этот оператор используется для деления объекта `CComCurrency`.  
  
```
CComCurrency operator/(long nOperand) const;
```  
  
### <a name="parameters"></a>Параметры  
 `nOperand`  
 Делитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CComCurrency` объект, представляющий результат деления. Если делитель равен 0, произойдет сбой assert.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#59;](../../atl/codesnippet/cpp/ccomcurrency-class_7.cpp)]  
  
##  <a name="operator_div_eq"></a>CComCurrency::operator / =  
 Этот оператор используется для деления объекта `CComCurrency` и назначения ему результата.  
  
```
const CComCurrency& operator/= (long nOperand);
```  
  
### <a name="parameters"></a>Параметры  
 `nOperand`  
 Делитель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CComCurrency` объекта. Если делитель равен 0, произойдет сбой assert.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#60;](../../atl/codesnippet/cpp/ccomcurrency-class_8.cpp)]  
  
##  <a name="operator_add"></a>CComCurrency::operator +  
 Этот оператор используется для сложения объекта `CComCurrency`.  
  
```
CComCurrency operator+(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 `CComCurrency` Объект, добавляемый к исходному объекту.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `CComCurrency` объект, представляющий результат сложения. В случае возникновения ошибки, например переполнение, вызывает этот оператор `AtlThrow` с описанием ошибки HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#61;](../../atl/codesnippet/cpp/ccomcurrency-class_9.cpp)]  
  
##  <a name="operator_add_eq"></a>CComCurrency::operator +=  
 Этот оператор используется для сложения объекта `CComCurrency` и назначения ему результата.  
  
```
const CComCurrency& operator+= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 Объект `CComCurrency`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CComCurrency` объекта. В случае возникновения ошибки, например переполнение, вызывает этот оператор `AtlThrow` с описанием ошибки HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#62;](../../atl/codesnippet/cpp/ccomcurrency-class_10.cpp)]  
  
##  <a name="operator_lt"></a>CComCurrency::operator&lt;  
 Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить меньший из них.  
  
```
bool operator<(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 Объект `CComCurrency`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект меньше, чем второй, **false** в противном случае.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#63;](../../atl/codesnippet/cpp/ccomcurrency-class_11.cpp)]  
  
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
 [!code-cpp[NVC_ATL_Utilities&#64;](../../atl/codesnippet/cpp/ccomcurrency-class_12.cpp)]  
  
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
 Возвращает обновленный `CComCurrency` объекта. В случае возникновения ошибки, например переполнение, вызывает этот оператор `AtlThrow` с описанием ошибки HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#65;](../../atl/codesnippet/cpp/ccomcurrency-class_13.cpp)]  
  
##  <a name="operator_-_eq"></a>CComCurrency::operator-=  
 Этот оператор используется для вычитания объекта `CComCurrency` и назначения ему результата.  
  
```
const CComCurrency& operator-= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 Объект `CComCurrency`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CComCurrency` объекта. В случае возникновения ошибки, например переполнение, вызывает этот оператор `AtlThrow` с описанием ошибки HRESULT.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#66;](../../atl/codesnippet/cpp/ccomcurrency-class_14.cpp)]  
  
##  <a name="operator_eq_eq"></a>CComCurrency::operator ==  
 Этот оператор сравнивает два объекта `CComCurrency` на равенство.  
  
```
bool operator== (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 `CComCurrency` Объект для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если объекты равны (то есть, `m_currency` элементы данных, как integer и долей в обоих объектов имеют одинаковое значение), **false** в противном случае.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#67;](../../atl/codesnippet/cpp/ccomcurrency-class_15.cpp)]  
  
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
 [!code-cpp[NVC_ATL_Utilities&#68;](../../atl/codesnippet/cpp/ccomcurrency-class_16.cpp)]  
  
##  <a name="operator_gt_eq"></a>CComCurrency::operator&gt;=  
 Этот оператор сравнивает два объекта `CComCurrency`, чтобы определить равенство или больший из них.  
  
```
bool operator>= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Параметры  
 `cur`  
 Объект `CComCurrency`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **true** Если первый объект больше или равен второму, **false** в противном случае.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#69;](../../atl/codesnippet/cpp/ccomcurrency-class_17.cpp)]  
  
##  <a name="operator_currency"></a>CComCurrency::operator ВАЛЮТ  
 Эти операторы используются для приведения `CComCurrency` объект **валюты** тип данных.  
  
```  
operator CURRENCY&() throw();
operator const CURRENCY&() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на **валюты** объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#70;](../../atl/codesnippet/cpp/ccomcurrency-class_18.cpp)]  
  
##  <a name="round"></a>CComCurrency::Round  
 Этот метод вызывается для округления валюты указанного количества десятичных разрядов.  
  
```
HRESULT Roundint nDecimals);
```  
  
### <a name="parameters"></a>Параметры  
 *nDecimals*  
 Число цифр, к которому `m_currency` будет округляться в диапазоне от 0 до 4.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#52;](../../atl/codesnippet/cpp/ccomcurrency-class_19.cpp)]  
  
##  <a name="setfraction"></a>CComCurrency::SetFraction  
 Вызовите этот метод для установки дробной части объекта `CComCurrency`.  
  
```
HRESULT SetFraction(SHORT nFraction);
```  
  
### <a name="parameters"></a>Параметры  
 *nFraction*  
 Значение, присваиваемое дробная часть `m_currency` элемента данных. Знак дробная должно быть таким же, как целочисленный, а значение должно быть в диапазоне от-( **CY_MIN_FRACTION**) для +9999 ( **CY_MAX_FRACTION**).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#53;](../../atl/codesnippet/cpp/ccomcurrency-class_20.cpp)]  
  
##  <a name="setinteger"></a>CComCurrency::SetInteger  
 Вызовите этот метод для установки целой части объекта `CComCurrency`.  
  
```
HRESULT SetInteger(LONGLONG nInteger);
```  
  
### <a name="parameters"></a>Параметры  
 `nInteger`  
 Значение, присваиваемое целочисленный `m_currency` члена данных. Знак целочисленный должен совпадать со знаком существующего компонента долей.  
  
 `nInteger`должно быть в диапазоне **CY_MIN_INTEGER** для **CY_MAX_INTEGER** включительно. Эти значения определяются в atlcur.h.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#54;](../../atl/codesnippet/cpp/ccomcurrency-class_21.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс COleCurrency](../../mfc/reference/colecurrency-class.md)   
 [ВАЛЮТА](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

