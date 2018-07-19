---
title: Класс auto_gcroot | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b6afad3450aff2a9243b3e4a480a374fbcd14fc7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103870"
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