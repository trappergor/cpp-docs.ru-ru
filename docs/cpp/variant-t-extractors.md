---
title: средства извлечения _variant_t | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t.operatordouble
- operatorlong
- _variant_t::operator_bstr_t
- operatordouble
- _variant_t.operatorCY
- operatorCY
- _variant_t::operatorCY
- _variant_t::operatordouble
- operatorfloat
- operatorBYTE
- _variant_t.operatorDECIMAL
- _variant_t::operatorlong
- operatorIDispatch
- _variant_t.operatorBYTE
- operatorDECIMAL
- _variant_t.operator_bstr_t
- _variant_t::operatorDECIMAL
- _variant_t.operatorIUnknown
- _variant_t.operatorlong
- _variant_t::operatorIDispatch
- _variant_t::operatorIUnknown
- operatorIUnknown
- _variant_t.operatorbool
- _variant_t::operatorBYTE
- _variant_t.operatorfloat
- operator_bstr_t
- _variant_t::operatorbool
- operatorshort
- _variant_t::operatorshort
- _variant_t::operatorfloat
- _variant_t.operatorIDispatch
- _variant_t.operatorshort
dev_langs:
- C++
helpviewer_keywords:
- extractors, _variant_t class
- operator CY
- operator IDispatch
- operator SHORT
- operator double
- operator long
- operator _bstr_t
- operator DECIMAL
- operator float
- operator bool
- operator BYTE
- operator IUnknown
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 65049a473f62e728fcb4d74b581a08c0f1723fc9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="variantt-extractors"></a>Средства извлечения _variant_t
**Блок, относящийся только к системам Microsoft**  
  
 Извлечение данных из инкапсулированного **VARIANT** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
operator short( ) const;   
operator long( ) const;   
operator float( ) const;   
operator double( ) const;   
operator CY( ) const;   
operator _bstr_t( ) const;   
operator IDispatch*( ) const;   
operator bool( ) const;   
operator IUnknown*( ) const;   
operator DECIMAL( ) const;   
operator BYTE( ) const;  
operator VARIANT() const throw();  
operator char() const;  
operator unsigned short() const;  
operator unsigned long() const;  
operator int() const;  
operator unsigned int() const;  
operator __int64() const;  
operator unsigned __int64() const;  
```  
  
## <a name="remarks"></a>Примечания  
 Извлекает необработанные данные из инкапсулированного **VARIANT**. Если **VARIANT** еще не соответствующего типа **VariantChangeType** используется для выполнения попытки преобразования, и выводится сообщение об ошибке при сбое:  
  
-   **Operator short ()** извлекает **короткие** целочисленное значение.  
  
-   **Operator long ()** извлекает **длинные** целочисленное значение.  
  
-   **operator float ()** извлекает **float** числовое значение.  
  
-   **Operator double ()** извлекает **двойные** целочисленное значение.  
  
-   **Operator CY ()** извлекает **CY** объекта.  
  
-   **Operator bool ()** извлекает `bool` значение.  
  
-   **Operator DECIMAL ()** извлекает **ДЕСЯТИЧНОЕ** значение.  
  
-   **Operator BYTE ()** извлекает **БАЙТОВ** значение.  
  
-   **(оператор _bstr_t)** извлекает строку, которая инкапсулируется в `_bstr_t` объекта.  
  
-   **Operator IDispatch\*()** извлекает указатель на disp-интерфейса из инкапсулированного **VARIANT**. `AddRef` вызывается для результирующего указателя, поэтому его освобождения следует вызвать метод **выпуска** для его освобождения.  
  
-   **Operator IUnknown\*()** извлекает из инкапсулированного указателя интерфейса СОМ **VARIANT**. `AddRef` вызывается для результирующего указателя, поэтому его освобождения следует вызвать метод **выпуска** для его освобождения.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _variant_t](../cpp/variant-t-class.md)
