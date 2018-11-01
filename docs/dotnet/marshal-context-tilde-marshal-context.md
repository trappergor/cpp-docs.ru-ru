---
title: marshal_context::~marshal_context
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- marshal_context::~marshal_context
- msclr.interop.marshal_context.~marshal_context
- marshal_context.~marshal_context
- msclr::interop::marshal_context::~marshal_context
- ~marshal_context
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 34c41b38-4c33-4f61-b74e-831ac46b4ab5
ms.openlocfilehash: 3bf16ab2dde4047fb845cd700821d097f733a4d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528223"
---
# <a name="marshalcontextmarshalcontext"></a>marshal_context::~marshal_context

Уничтожает объект `marshal_context`.

## <a name="syntax"></a>Синтаксис

```
~marshal_context();
```

## <a name="remarks"></a>Примечания

Некоторые преобразования данных требуется контекст маршалинга. См. в разделе [Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md) Дополнительные сведения о какой переводы требуется контекст и какие маршалинга файл должен быть включены в приложении.

Удаление `marshal_context` объект сделает данные, преобразованные в этом контексте. Если вы хотите сохранить данные после `marshal_context` уничтожении объекта, необходимо вручную скопировать данные на переменную, которая будет сохраняться.

## <a name="requirements"></a>Требования

**Файл заголовка:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, или \<msclr\marshal_atl.h >

**Пространство имен:** msclr::interop

## <a name="see-also"></a>См. также

[Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_as](../dotnet/marshal-as.md)<br/>
[Класс marshal_context](../dotnet/marshal-context-class.md)