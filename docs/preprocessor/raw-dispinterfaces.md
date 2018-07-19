---
title: raw_dispinterfaces | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- raw_dispinterfaces
dev_langs:
- C++
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f2a0d91d0f0dd3d23886ade75072526e6c895f7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849458"
---
# <a name="rawdispinterfaces"></a>raw_dispinterfaces
**Конкретных C++**  
  
 Указывает компилятору сгенерировать низкоуровневые функции оболочки для disp-интерфейса методов и свойств, которые вызывают **IDispatch::Invoke** и возвращают `HRESULT` код ошибки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
raw_dispinterfaces  
```  
  
## <a name="remarks"></a>Примечания  
 Если этот атрибут не указан, создаются только высокоуровневые оболочки, которые в случае сбоя вызывают исключения C++.  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)