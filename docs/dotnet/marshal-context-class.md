---
title: Класс marshal_context | Документация Майкрософт
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
ms.openlocfilehash: fc3399ee088a0430ca857c3e421742ee484d337a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413320"
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