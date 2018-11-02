---
title: Компилятор предупреждение (уровень 3) C4192
ms.date: 11/04/2016
f1_keywords:
- C4192
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
ms.openlocfilehash: 56b27596296b87edcc6de406e7b6621d5723815d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519721"
---
# <a name="compiler-warning-level-3-c4192"></a>Компилятор предупреждение (уровень 3) C4192

автоматическое исключение «name» при импорте библиотеки типов «библиотека»

Объект `#import` библиотека содержит элемент, *имя*, то есть также определены в заголовках системы Win32. Из-за ограничений библиотек типов, имена, такие как **IUnknown** или GUID часто определяются в библиотеке типов, дублирует определения системных заголовочных файлах. `#import` обнаружит эти элементы и не будет встраивать их в TLH-файлы и TLI-файлы.

Чтобы переопределить это поведение, используйте `#import` атрибуты [no_auto_exclude](../../preprocessor/no-auto-exclude.md) и [include()](../../preprocessor/include-parens.md).