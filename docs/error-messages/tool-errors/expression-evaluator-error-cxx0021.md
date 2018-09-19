---
title: Ошибка вычислителя выражений CXX0021 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0021
dev_langs:
- C++
helpviewer_keywords:
- CXX0021
- CAN0021
ms.assetid: d6c0c35a-16c2-42c0-a7d2-e910350a47f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ef765286d022b26aeed0ca98c9f43f94f5d17f8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025780"
---
# <a name="expression-evaluator-error-cxx0021"></a>Ошибка вычислителя выражений CXX0021

структуры или объединения как скаляра

Структура или объединение был использован в выражении, но не указан элемент.

При обработке структуры или объединения, имя переменной может отображаться самостоятельно, без квалификатора поля. Если в выражении используется структура или объединение, он должны быть дополнены конкретного необходимого элемента.

Укажите элемент, значение которого будет использоваться в выражении.

Эта ошибка идентична ошибке CAN0021.