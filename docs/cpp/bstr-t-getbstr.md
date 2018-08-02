---
title: _bstr_t::GetBSTR | Документация Майкрософт
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
ms.openlocfilehash: 8863f3a6c37693ec28f931c2af4cb0d299788daa
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402667"
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
 **GetBSTR** влияет на все `_bstr_t` объектов данной общей папки `BSTR`. Более одного `_bstr_t` могут совместно использовать `BSTR` при помощи конструктора копии и и **оператор =**.  
  
## <a name="example"></a>Пример  
 См. в разделе [_bstr_t::Assign](../cpp/bstr-t-assign.md) в качестве примера использования **GetBSTR**.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_bstr_t Class](../cpp/bstr-t-class.md)