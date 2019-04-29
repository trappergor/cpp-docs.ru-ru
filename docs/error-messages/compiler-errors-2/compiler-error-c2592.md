---
title: Ошибка компилятора C2592
ms.date: 11/04/2016
f1_keywords:
- C2592
helpviewer_keywords:
- C2592
ms.assetid: 833a4d7b-66ef-4d4c-ae83-a533c2b0eb07
ms.openlocfilehash: 2ea5919f073f2fd608dca332e721be0669760a0a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387023"
---
# <a name="compiler-error-c2592"></a>Ошибка компилятора C2592

class: base_class_2 наследуется от base_class_1 и не может быть указан повторно

Можно указать только базовые классы, которые не наследуют от других базовых классов. В данном случае в описании `class` требуется только `base_class_1`, так как `base_class_1` уже наследует `base_class_2`.