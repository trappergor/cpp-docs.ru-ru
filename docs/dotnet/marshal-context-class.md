---
title: Класс marshal_context
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- marshal_context
helpviewer_keywords:
- marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
ms.openlocfilehash: 0e25aee0996b0cd16ca92566da22d377b762d7bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594536"
---
# <a name="marshalcontext-class"></a>Класс marshal_context

Этот класс преобразует данные между собственной и управляемой средами.

## <a name="syntax"></a>Синтаксис

```
class marshal_context
```

## <a name="remarks"></a>Примечания

Используйте `marshal_context` класс для преобразования данных, требуется контекст. См. в разделе [Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md) Дополнительные сведения о какие преобразования требуется контекст и маршалинга файл, который должен быть вставлен. Результат операций маршалинга при использовании контекста действителен только до `marshal_context` уничтожении объекта. Для сохранения результатов, необходимо скопировать данные.

Же `marshal_context` можно использовать для нескольких преобразований данных. Повторное использование контекста таким образом не повлияет на результаты предыдущих маршалинга вызовов.

## <a name="requirements"></a>Требования

**Файл заголовка:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, или \<msclr\marshal_atl.h >

**Пространство имен:** msclr::interop

## <a name="see-also"></a>См. также

[Общие сведения о маршалинге в C++](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_as](../dotnet/marshal-as.md)