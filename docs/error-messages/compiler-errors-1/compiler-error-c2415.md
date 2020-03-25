---
title: Ошибка компилятора C2415
ms.date: 11/04/2016
f1_keywords:
- C2415
helpviewer_keywords:
- C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
ms.openlocfilehash: a0cdd528eca8ea267c62e6d44752d29ae16830c4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205625"
---
# <a name="compiler-error-c2415"></a>Ошибка компилятора C2415

Недопустимый тип операнда

Код операции не использует операнды этого типа.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Код операции не поддерживает число используемых операндов. Проверьте руководство по языку сборки, чтобы определить правильное число операндов.

1. Новый процессор поддерживает инструкцию с дополнительными типами. Настройте параметр [/Arch (минимальная архитектура ЦП)](../../build/reference/arch-minimum-cpu-architecture.md) , чтобы использовать более поздний процессор.
