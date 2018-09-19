---
title: Ошибка вычислителя выражений CXX0030 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0030
dev_langs:
- C++
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb2921013d116b7d8f02e1e29380ca3cd14086b9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102818"
---
# <a name="expression-evaluator-error-cxx0030"></a>Ошибка вычислителя выражений CXX0030

невычислимое выражение

Вычислитель выражений отладчика не удалось получить значение для выражения, по мере записи. Возможной причиной является то, что выражение ссылается на область памяти, который находится вне адресного пространства программы (разыменования указателя null является одним из примеров). Windows не поддерживает доступ к памяти за пределами адресном пространстве программы.

Можно переписать выражение с помощью скобок для управления порядком вычисления.

Эта ошибка идентична ошибке CAN0030.