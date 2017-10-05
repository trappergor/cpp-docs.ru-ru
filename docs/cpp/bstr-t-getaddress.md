---
title: "_bstr_t::GetAddress | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetAddress
dev_langs:
- C++
helpviewer_keywords:
- GetAddress method
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
caps.latest.revision: 7
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: d11479a93cf19b59ae6b824f76f9b00b10fff6b2
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="bstrtgetaddress"></a>_bstr_t::GetAddress
**Блок, относящийся только к системам Майкрософт**  
  
 Освобождает любую существующую строку и возвращает адрес новой строки, которой была выделена память.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
BSTR* GetAddress( );  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку `BSTR`, инкапсулированную объектом `_bstr_t`.  
  
## <a name="remarks"></a>Примечания  
 Функция `GetAddress` действует на все объекты `_bstr_t`, которые совместно используют строку `BSTR`. Одну и ту же строку `_bstr_t` может совместно использовать несколько объектов `BSTR`. Это делается при помощи конструктора копии и `operator=`.  
  
## <a name="example"></a>Пример  
 В разделе [_bstr_t::Assign](../cpp/bstr-t-assign.md) пример использования `GetAddress`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_bstr_t Class](../cpp/bstr-t-class.md)
