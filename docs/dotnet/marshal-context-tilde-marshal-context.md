---
title: 'marshal_context:: ~ marshal_context | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- marshal_context::~marshal_context
- msclr.interop.marshal_context.~marshal_context
- marshal_context.~marshal_context
- msclr::interop::marshal_context::~marshal_context
- ~marshal_context
dev_langs:
- C++
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 34c41b38-4c33-4f61-b74e-831ac46b4ab5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a6cb7ed3c7b1ee5b28c4943d83b6a8ca6166b6d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="marshalcontextmarshalcontext"></a>marshal_context::~marshal_context
Уничтожает объект `marshal_context`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
~marshal_context();  
```  
  
## <a name="remarks"></a>Примечания  
 Некоторые преобразования данных требуется контекст маршалинга. В разделе [Обзор из маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md) Дополнительные сведения о какой переводы требуется контекст и какие маршалинга файл содержит должны быть включены в приложение.  
  
 Удаление `marshal_context` объекта сделает данные, преобразованные в этом контексте. Если вы хотите сохранить данные после `marshal_context` объект уничтожается, необходимо вручную скопировать данные переменной, которая будет сохраняться.  
  
## <a name="requirements"></a>Требования  
 **Файл заголовка:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, или \<msclr\marshal_atl.h >  
  
 **Пространство имен:** msclr::interop  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)   
 [Класс marshal_context](../dotnet/marshal-context-class.md)