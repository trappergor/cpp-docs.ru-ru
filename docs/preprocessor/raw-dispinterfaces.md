---
title: "raw_dispinterfaces | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: raw_dispinterfaces
dev_langs: C++
helpviewer_keywords: raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3d92c6940c4eabc83143ce1054604ae4648347d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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