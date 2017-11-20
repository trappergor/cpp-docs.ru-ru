---
title: "_bstr_t::Detach | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _bstr_t::Detach
dev_langs: C++
helpviewer_keywords: Detach method [C++]
ms.assetid: cc8284bd-f68b-4fff-b2e6-ce8354dabf8b
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6d6a8120edb32a1000fd5eec1c1c9372d7c068e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="bstrtdetach"></a>_bstr_t::Detach
**Блок, относящийся только к системам Майкрософт**  
  
 Возвращает строку `BSTR`, инкапсулированную объектом `_bstr_t`, и отсоединяет ее (`BSTR`) от этого объекта (`_bstr_t`).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
BSTR Detach( ) throw;  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 `BSTR` в оболочке `_bstr_t`.  
  
## <a name="example"></a>Пример  
 В разделе [_bstr_t::Assign](../cpp/bstr-t-assign.md) пример использования **отсоединения**.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_bstr_t Class](../cpp/bstr-t-class.md)