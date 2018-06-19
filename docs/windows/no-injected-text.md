---
title: no_injected_text | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.no_injected_text
dev_langs:
- C++
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 74336ffaa5e1f9f1990acedf1669526c9152b82b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880352"
---
# <a name="noinjectedtext"></a>no_injected_text
Запрещает компилятору встраивать код в результате использования атрибута.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ no_injected_text(  
   boolean  
) ];  
```  
  
#### <a name="parameters"></a>Параметры  
 `boolean` (необязательно)  
 **значение true,** Если требуется, чтобы не коду, введенному, **false** для внедренным кодом. **значение true,** значение по умолчанию.  
  
## <a name="remarks"></a>Примечания  
 Чаще всего используют **no_injected_text** C++ атрибут должен быть, [/Fx](../build/reference/fx-merge-injected-code.md) параметр компилятора, который вставляет **no_injected_text** атрибута в MRG-файле.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|В любом месте|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты компилятора](../windows/compiler-attributes.md)   
