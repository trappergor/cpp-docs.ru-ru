---
title: raw_dispinterfaces | Документация Майкрософт
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
ms.openlocfilehash: 02133e6b9d884fa8e0a175dd01845035ec8b96a7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435952"
---
# <a name="rawdispinterfaces"></a>raw_dispinterfaces
**Конкретных C++**  
  
Указывает компилятору сгенерировать низкоуровневые функции оболочки для методов disp-интерфейса и свойства, которые вызывают `IDispatch::Invoke` и возвращают код ошибки HRESULT.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
raw_dispinterfaces  
```  
  
## <a name="remarks"></a>Примечания  
 
Если этот атрибут не указан, создаются только высокоуровневые оболочки, которые в случае сбоя вызывают исключения C++.  
  
**КОНЕЦ конкретных C++**  
  
## <a name="see-also"></a>См. также  
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)