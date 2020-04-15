---
title: Математическая ошибка M6108
ms.date: 11/04/2016
f1_keywords:
- M6108
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
ms.openlocfilehash: c6bd403437ee5e55eaf4add288995d0e4aa76c3b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361975"
---
# <a name="math-error-m6108"></a>Математическая ошибка M6108

квадратный корень

Операция в квадратном корню была отрицательной.

Программа завершается с кодом выхода 136.

> [!NOTE]
> Функция `sqrt` в библиотеке C run-time и внутренняя функция FORTRAN **S'RT** не генерирует эту ошибку. Функция `sqrt` C проверяет аргумент перед выполнением операции и возвращает значение ошибки, если действие отрицательное. Функция FORTRAN **S-RT** генерирует ошибку DOMAIN [M6201](../../error-messages/tool-errors/math-error-m6201.md) вместо этой ошибки.
