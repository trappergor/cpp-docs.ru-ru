---
title: Класс marshal_context | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- marshal_context
dev_langs:
- C++
helpviewer_keywords:
- marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6bf712e960cbf96ccef6c3a3e4efebdad9045818
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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