---
title: Математическая ошибка M6108
ms.date: 11/04/2016
f1_keywords:
- M6108
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
ms.openlocfilehash: d60e9b6284c79828fda1f7af542fcf197f189ad0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451016"
---
# <a name="math-error-m6108"></a>Математическая ошибка M6108

квадратный корень

Операнд в операции квадратный корень было отрицательным.

Программа завершается с кодом выхода 136.

> [!NOTE]
>  `sqrt` Функции в библиотеке времени выполнения C и встроенная функция FORTRAN **SQRT** не создают эту ошибку. C `sqrt` функция проверяет аргумент перед выполнением операции и возвращает значение ошибки, если операнд является отрицательным. FORTRAN **SQRT** функция создает ошибку домена [M6201](../../error-messages/tool-errors/math-error-m6201.md) вместо этой ошибки.