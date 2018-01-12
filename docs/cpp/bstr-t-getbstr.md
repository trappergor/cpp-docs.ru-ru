---
title: "_bstr_t::GetBSTR | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _bstr_t::GetBSTR
dev_langs: C++
helpviewer_keywords: GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 00b2f7f487673c67aa7b681499462ea05a471b48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="bstrtgetbstr"></a>_bstr_t::GetBSTR
**Блок, относящийся только к системам Microsoft**  
  
 Указывает на начало строки `BSTR`, инкапсулированной объектом `_bstr_t`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
BSTR& GetBSTR( );  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Начало строки `BSTR`, инкапсулированной объектом `_bstr_t`.  
  
## <a name="remarks"></a>Примечания  
 Функция `GetBSTR` действует на все объекты `_bstr_t`, которые совместно используют строку `BSTR`. Одну и ту же строку `_bstr_t` может совместно использовать несколько объектов `BSTR`. Это делается при помощи конструктора копии и `operator=`.  
  
## <a name="example"></a>Пример  
 В разделе [_bstr_t::Assign](../cpp/bstr-t-assign.md) пример использования `GetBSTR`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_bstr_t Class](../cpp/bstr-t-class.md)