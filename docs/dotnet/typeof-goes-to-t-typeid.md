---
title: Переход TypeOf в T::typeid | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- typeid operator
- __typeof keyword
- typeid keyword [C++]
ms.assetid: 6a0d35a7-7a1a-4070-b187-cff37cfdc205
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4433061fceef455685b6588c81c8c2e434253433
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374683"
---
# <a name="typeof-goes-to-ttypeid"></a>Переход typeof в T::typeid

`typeof` Оператор, используемый в управляемых расширениях для C++ были заменены `typeid` ключевого слова в Visual C++.

В управляемых расширениях `__typeof()` оператор возвращает связанный `Type*` объекта при передаче имени управляемого типа. Пример:

```
// Creates and initializes a new Array instance.
Array* myIntArray =
   Array::CreateInstance( __typeof(Int32), 5 );
```

В новом синтаксисе `__typeof` был заменен классом дополнительной формы `typeid` , возвращающий `Type^` при указании управляемый тип.

```
// Creates and initializes a new Array instance.
Array^ myIntArray =
   Array::CreateInstance( Int32::typeid, 5 );
```

## <a name="see-also"></a>См. также

[Общие изменения в языке (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)<br/>
[typeid](../windows/typeid-cpp-component-extensions.md)