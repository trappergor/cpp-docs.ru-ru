---
title: Неустранимая ошибка C1013 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1013
dev_langs:
- C++
helpviewer_keywords:
- C1013
ms.assetid: 5514a679-efe7-4055-bdd3-5693ca0c332f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33c10062cac83984fb1c68835780497b89c4cbc1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050525"
---
# <a name="fatal-error-c1013"></a>Неустранимая ошибка C1013

ограничение компилятора: слишком много открывающих круглых скобок

Выражение содержит слишком много уровней круглых скобок в одном выражении. Упростите выражение или разбейте его на несколько инструкций.

До Visual C++ 6.0 с пакетом обновления 3 в одном выражении могло быть не более 59 вложенных круглых скобок. В настоящее время ограничение на количество круглых скобок увеличено до 256.