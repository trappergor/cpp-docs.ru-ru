---
title: marshal_context::marshal_context
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::interop::marshal_context::marshal_context
- marshal_context::marshal_context
- msclr.interop.marshal_context.marshal_context
- marshal_context.marshal_context
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 5f08c895-60b0-4f72-97ff-7ae37c68e853
ms.openlocfilehash: a1a62c47450224aa2bcacde75038adf7a8cfbb9d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532591"
---
# <a name="marshalcontextmarshalcontext"></a>marshal_context::marshal_context

Создает `marshal_context` объект, используемый для преобразования данных между типами данных, управляемый и машинный.

## <a name="syntax"></a>Синтаксис

```
marshal_context();
```

## <a name="remarks"></a>Примечания

Некоторые преобразования данных требуется контекст маршалинга. См. в разделе [Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md) Дополнительные сведения о какой переводы требуется контекст и какие маршалинга файл должен быть включены в приложении.

## <a name="example"></a>Пример

См. в примере [marshal_context::marshal_as](../dotnet/marshal-context-marshal-as.md).

## <a name="requirements"></a>Требования

**Файл заголовка:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, или \<msclr\marshal_atl.h >

**Пространство имен:** msclr::interop

## <a name="see-also"></a>См. также

[Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_as](../dotnet/marshal-as.md)<br/>
[Класс marshal_context](../dotnet/marshal-context-class.md)