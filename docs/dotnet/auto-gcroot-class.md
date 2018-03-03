---
title: "Класс auto_gcroot | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot
- msclr.auto_gcroot
- auto_gcroot
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot
ms.assetid: b5790912-265d-463e-a486-47302e91042a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bb203193d1568056c631d90a2e1f5b1cf1d00e5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="autogcroot-class"></a>Класс auto_gcroot
Управлять ресурсами в автоматическом (такие как [класс auto_ptr](../standard-library/auto-ptr-class.md)) который можно использовать для внедрения виртуальный дескриптор в собственный тип.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename _element_type>  
class auto_gcroot;  
```  
  
#### <a name="parameters"></a>Параметры  
 `_element_type`  
 Управляемый тип для внедрения.  
  
## <a name="requirements"></a>Требования  
 **Файл заголовка** \<msclr\auto_gcroot.h >  
  
 **Пространство имен** msclr  
  
## <a name="see-also"></a>См. также  
 [auto_gcroot](../dotnet/auto-gcroot.md)   
 [Члены auto_gcroot](../dotnet/auto-gcroot-members.md)   
 [Как: объявление дескрипторов в собственных типах](../dotnet/how-to-declare-handles-in-native-types.md)   
 [Класс auto_handle](../dotnet/auto-handle-class.md)