---
title: Компоновка статической константы Int больше не является литералом | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- literal attribute [C++]
- constants, declaring
- integral constant expressions
ms.assetid: d2a5e3d2-ffb0-4b61-8114-bec5993a1195
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c51853274b061ba290ff90993f45ccdf3375349b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431298"
---
# <a name="static-const-int-linkage-is-no-longer-literal"></a>Компоновка статической константы Int больше не является литералом

Объявление констант члена класса отличается от управляемых расширений для C++ в Visual C++.

Несмотря на то что `static const` целочисленные члены по-прежнему поддерживаются, их атрибут компоновки изменился. Прежний атрибут компоновки теперь выполняется в отдельном целочисленный литерал. Например рассмотрим следующий класс управляемых расширений:

```
public __gc class Constants {
public:
   static const int LOG_DEBUG = 4;
};
```

Это создает следующие основные атрибуты CIL для поля (Обратите внимание, литерального атрибута):

```
.field public static literal int32
modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)
```

Хотя это по-прежнему компилируется в новом синтаксисе:

```
public ref class Constants {
public:
   static const int LOG_DEBUG = 4;
};
```

он больше не выдает литерального атрибута и поэтому не отображается как константа средой выполнения CLR:

```
.field public static int32 modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)
```

Чтобы получить такой же межъязыковой атрибут-литерал, необходимо изменить объявление новым поддерживаемым `literal` элемент данных, следующим образом:

```
public ref class Constants {
public:
   literal int LOG_DEBUG = 4;
};
```

## <a name="see-also"></a>См. также

[Объявления членов в пределах класса или интерфейса (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[литерал](../windows/literal-cpp-component-extensions.md)