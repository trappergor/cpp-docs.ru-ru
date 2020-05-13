---
title: Предупреждение компилятора (уровень 3) C4192
ms.date: 11/04/2016
f1_keywords:
- C4192
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
ms.openlocfilehash: 38b346e0a90729bda431b9cb578a03806be1ea4c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198982"
---
# <a name="compiler-warning-level-3-c4192"></a>Предупреждение компилятора (уровень 3) C4192

автоматически исключить "Name" при импорте библиотеки типов "Library"

Библиотека `#import` содержит элемент *Name*, который также определен в заголовках системы Win32. Из-за ограничений библиотек типов такие имена, как **IUnknown** или GUID, часто определяются в библиотеке типов, что приводит к дублированию определения из системных заголовков. `#import` обнаружит эти элементы и отказались от их включения в файлы заголовков TLH и тли.

Чтобы переопределить это поведение, используйте атрибуты `#import` [no_auto_exclude](../../preprocessor/no-auto-exclude.md) и [include ()](../../preprocessor/include-parens.md).
