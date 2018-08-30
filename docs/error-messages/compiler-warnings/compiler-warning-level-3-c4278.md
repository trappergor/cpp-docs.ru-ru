---
title: Предупреждение компилятора (уровень 3) C4278 | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4278
dev_langs:
- C++
helpviewer_keywords:
- C4278
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f63337de2e14b1cb0f9d854df962ab2aa9c8014e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205785"
---
# <a name="compiler-warning-level-3-c4278"></a>Предупреждение компилятора (уровень 3) C4278

> "*идентификатор*": идентификатор в библиотеке типов "*tlb*" уже является макроопределением; используйте квалификатор «rename»

При использовании [#import](../../preprocessor/hash-import-directive-cpp.md), идентификатор в библиотеке типов, импортируемой пытается объявить идентификатор *идентификатор*. Тем не менее это уже допустимый символ.

Используйте `#import` **Переименовать** атрибута позволяют назначить псевдоним для символа в библиотеке типов.