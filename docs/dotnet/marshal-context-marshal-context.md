---
title: marshal_context::marshal_context | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::interop::marshal_context::marshal_context
- marshal_context::marshal_context
- msclr.interop.marshal_context.marshal_context
- marshal_context.marshal_context
dev_langs:
- C++
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 5f08c895-60b0-4f72-97ff-7ae37c68e853
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1e8838864c4ec1c6414401608b848cb12b01c16e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33140124"
---
# <a name="marshalcontextmarshalcontext"></a>marshal_context::marshal_context
Создает `marshal_context` объект, который используется для преобразования данных между типами данных управляемый и машинный.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
marshal_context();  
```  
  
## <a name="remarks"></a>Примечания  
 Некоторые преобразования данных требуется контекст маршалинга. В разделе [Обзор из маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md) Дополнительные сведения о какой переводы требуется контекст и какие маршалинга файл содержит должны быть включены в приложение.  
  
## <a name="example"></a>Пример  
 Далее приведен пример [marshal_context::marshal_as](../dotnet/marshal-context-marshal-as.md).  
  
## <a name="requirements"></a>Требования  
 **Файл заголовка:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, или \<msclr\marshal_atl.h >  
  
 **Пространство имен:** msclr::interop  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)   
 [Класс marshal_context](../dotnet/marshal-context-class.md)