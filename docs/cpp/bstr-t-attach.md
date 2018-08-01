---
title: _bstr_t::Attach | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9f69811b7b25a793d11ef6d53aaf0638c752a11
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409109"
---
# <a name="bstrtattach"></a>_bstr_t::Attach
**Блок, относящийся только к системам Microsoft**  
  
 Связывает упаковщик `_bstr_t` со строкой `BSTR`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void Attach(  
   BSTR s  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *s*  
 Ресурс `BSTR` для связывания с переменной `_bstr_t` или назначения ей.  
  
## <a name="remarks"></a>Примечания  
 Если переменная `_bstr_t` была ранее присоединена к другому ресурсу `BSTR`, `_bstr_t` очистит ресурсы `BSTR`, если другие переменные `_bstr_t` не используют `BSTR`.  
  
## <a name="example"></a>Пример  
 См. в разделе [_bstr_t::Assign](../cpp/bstr-t-assign.md) в качестве примера использования **Attach**.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_bstr_t Class](../cpp/bstr-t-class.md)