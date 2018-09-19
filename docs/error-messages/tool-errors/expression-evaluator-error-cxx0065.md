---
title: Ошибка вычислителя выражений CXX0065 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0065
dev_langs:
- C++
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c100b1edbd36f4384e8deb1abf5b36465e8da479
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024168"
---
# <a name="expression-evaluator-error-cxx0065"></a>Ошибка вычислителя выражений CXX0065

переменная должна кадр стека

Выражение содержит переменную, которая существует в текущей области, но еще не создана.

Эта ошибка может возникать, если вы выполнили шаг с заходом в прологе функции, но еще не настройте кадр стека для функции или если вы выполнили шаг с заходом в код выхода из функции.

Пройдите по код пролога до настройки кадр стека перед вычислением выражения.

Эта ошибка идентична ошибке CAN0065.