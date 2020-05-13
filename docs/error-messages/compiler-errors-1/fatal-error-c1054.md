---
title: Неустранимая ошибка C1054
ms.date: 11/04/2016
f1_keywords:
- C1054
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
ms.openlocfilehash: d094d0892d43a5f9894f03538f72e59b57bad6db
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204468"
---
# <a name="fatal-error-c1054"></a>Неустранимая ошибка C1054

ограничение компилятора: недопустимая степень вложения инициализаторов

В коде превышено ограничение вложенности для инициализаторов (уровни 10-15, в зависимости от сочетания типов, которые инициализируются).

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Упростите инициализацию типов данных, чтобы сократить число вложений.

1. Инициализируйте переменные в отдельных инструкциях после объявления.
