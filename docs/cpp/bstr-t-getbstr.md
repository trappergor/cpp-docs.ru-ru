---
title: _bstr_t::GetBSTR | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::GetBSTR
dev_langs:
- C++
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2c9903170f62652357264a3ea2de0839496e9e2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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