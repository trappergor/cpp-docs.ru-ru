---
title: _bstr_t::Attach | Документы Microsoft
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
ms.openlocfilehash: eeb114a33d3ac356bff16aeab47b8d894b7513e6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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
 В разделе [_bstr_t::Assign](../cpp/bstr-t-assign.md) пример использования **присоединение**.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_bstr_t Class](../cpp/bstr-t-class.md)