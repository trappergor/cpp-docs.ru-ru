---
title: Ошибка компилятора C2592 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2592
dev_langs:
- C++
helpviewer_keywords:
- C2592
ms.assetid: 833a4d7b-66ef-4d4c-ae83-a533c2b0eb07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f2377f48eb8102771705f2dedc67a7a15f6fa95
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030998"
---
# <a name="compiler-error-c2592"></a>Ошибка компилятора C2592

class: base_class_2 наследуется от base_class_1 и не может быть указан повторно

Можно указать только базовые классы, которые не наследуют от других базовых классов. В данном случае в описании `class` требуется только `base_class_1`, так как `base_class_1` уже наследует `base_class_2`.