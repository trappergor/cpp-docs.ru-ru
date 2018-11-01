---
title: Ошибка вычислителя выражений CXX0065
ms.date: 11/04/2016
f1_keywords:
- CXX0065
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
ms.openlocfilehash: 7b62e42da2a74d910e2dc56ce2dfcb5cb38f2bfa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571786"
---
# <a name="expression-evaluator-error-cxx0065"></a>Ошибка вычислителя выражений CXX0065

переменная должна кадр стека

Выражение содержит переменную, которая существует в текущей области, но еще не создана.

Эта ошибка может возникать, если вы выполнили шаг с заходом в прологе функции, но еще не настройте кадр стека для функции или если вы выполнили шаг с заходом в код выхода из функции.

Пройдите по код пролога до настройки кадр стека перед вычислением выражения.

Эта ошибка идентична ошибке CAN0065.