---
title: Неустранимая ошибка C1307
ms.date: 11/04/2016
f1_keywords:
- C1307
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
ms.openlocfilehash: c7eb90c8e17408f6898ef7ff1a9d9e5efcafb4fa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203350"
---
# <a name="fatal-error-c1307"></a>Неустранимая ошибка C1307

программа была изменена после сбора данных о профилях

При использовании [/LTCG: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)Компоновщик обнаружил модуль ввода, который был перекомпилирован после/LTCG: PGINSTRUMENT, и что модуль был изменен на тот момент, когда существующие данные профиля больше не нужны. Например, если граф вызовов изменился в перекомпилированном модуле, компилятор создаст C1307.

Чтобы устранить эту ошибку, выполните/LTCG: PGINSTRUMENT, повтор всех тестовых запусков и выполните/LTCG: PGOPTIMIZE. Если не удается выполнить/LTCG: PGINSTRUMENT и повторить все тестовые запуски, используйте/LTCG: PGUPDATE вместо/LTCG: PGOPTIMIZE для создания оптимизированного образа.
