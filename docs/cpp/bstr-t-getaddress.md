---
title: "_bstr_t::GetAddress | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _bstr_t::GetAddress
dev_langs: C++
helpviewer_keywords: GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5921b3091532c63e3ba92d6e6e74f29a85123ac1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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