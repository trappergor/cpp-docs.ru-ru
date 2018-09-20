---
title: C + +/ CLI Migration Primer | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++/CLI Version 2
- upgrading Visual C++ applications, Managed Extensions for C++ to Visual C++ 2005 syntax
- migration [C++], C++/CLI Version 2
- Managed Extensions for C++, upgrading syntax
- C++/CLI Version 2, managed extensions
ms.assetid: 8ec926b5-73f6-4f0c-bcdf-5203d293849a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 88b32ea226971c0fa5b6d269a8992629c3c4de77
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385435"
---
# <a name="ccli-migration-primer"></a>Основы миграции C++/CLI

Это руководство по переносу ваших программ Visual C++ из управляемых расширений для C++ в Visual C++.

C + +/ CLI является расширением парадигмы программирования динамических компонентов, чтобы стандартные языка ISO-C++. Этом новом языке представлен целый рад существенных усовершенствований сравнению с управляемыми расширениями. Этот раздел содержит нумерованный перечень управляемых расширений функций языка C++ и их сопоставление с Visual C++, где такое отображение существует и отмечается этих конструкций, для которых соответствия не существует.

## <a name="in-this-section"></a>В этом разделе

[Обзор изменений (C++/CLI)](../dotnet/outline-of-changes-cpp-cli.md)<br/>
Общий краткий обзор краткий обзор изменений по пяти основным категориям.

[Ключевые слова языка (C++/CLI)](../dotnet/language-keywords-cpp-cli.md)<br/>
Рассматриваются изменения в ключевых словах языка, включая удаление двойного знака подчеркивания и появлением контекстные и составные ключевые слова.

[Управляемые типы (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)<br/>
Ищет в перечень изменений в объявлении из общих система типов (CTS) — Сюда входят изменения в объявлении классов, массивов (включая массивы параметров), перечислений и т. д.

[Объявления членов в пределах класса или интерфейса (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
Описание изменений, касающихся членов классов, таких как скалярные свойства, свойства индекса, операторы, делегаты и события.

[Типы значений и их режимы работы (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
Описание типов значений и нового семейства внутренних и закрепляющих указателей. Здесь также рассматриваются ряд существенных изменений в семантике например, внедрение неявной упаковки, неизменность упакованных типов значений и также исключение поддержки конструкторов по умолчанию внутри классов значений.

[Общие изменения в языке (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)<br/>
Подробно рассматриваются изменения, такие как поддержка нотации, строка литерала поведение и изменения в семантике между ISO-C++ и C + +/ CLI.

## <a name="see-also"></a>См. также

[Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
[Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)