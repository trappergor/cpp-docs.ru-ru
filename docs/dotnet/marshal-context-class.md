---
title: "Класс marshal_context | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: marshal_context
dev_langs: C++
helpviewer_keywords: marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9b59dfa82563a0c115f521bb881411981a30efc9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="marshalcontext-class"></a>Класс marshal_context
Этот класс преобразует данные между машинным и управляемым средами.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class marshal_context  
```  
  
## <a name="remarks"></a>Примечания  
 Используйте `marshal_context` класс для преобразования данных, которым требуется контекст. В разделе [Обзор из маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md) Дополнительные сведения о какие преобразования требуется контекст и маршалинга файл, который должен быть вставлен. Результат маршалинга при использовании контекста действителен только `marshal_context` объект удаляется. Для сохранения результатов, необходимо скопировать данные.  
  
 Соответствует `marshal_context` можно использовать для нескольких преобразований данных. Повторное использование контекста таким образом не повлияет на результаты из предыдущих вызовов маршалинга.  
  
## <a name="requirements"></a>Требования  
 **Файл заголовка:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, или \<msclr\marshal_atl.h >  
  
 **Пространство имен:** msclr::interop  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о маршалировании в C++](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)