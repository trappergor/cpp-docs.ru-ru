---
title: Предупреждение (уровень 3) C4192 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4192
dev_langs:
- C++
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 671a8c83dcadcaa89372e53b6c3d677c5810b4a5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114414"
---
# <a name="compiler-warning-level-3-c4192"></a>Компилятор предупреждение (уровень 3) C4192

автоматическое исключение «name» при импорте библиотеки типов «библиотека»

Объект `#import` библиотека содержит элемент, *имя*, то есть также определены в заголовках системы Win32. Из-за ограничений библиотек типов, имена, такие как **IUnknown** или GUID часто определяются в библиотеке типов, дублирует определения системных заголовочных файлах. `#import` обнаружит эти элементы и не будет встраивать их в TLH-файлы и TLI-файлы.

Чтобы переопределить это поведение, используйте `#import` атрибуты [no_auto_exclude](../../preprocessor/no-auto-exclude.md) и [include()](../../preprocessor/include-parens.md).