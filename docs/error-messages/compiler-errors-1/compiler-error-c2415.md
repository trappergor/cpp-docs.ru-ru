---
title: Ошибка компилятора C2415
ms.date: 11/04/2016
f1_keywords:
- C2415
helpviewer_keywords:
- C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
ms.openlocfilehash: 81e2da31b39b323919132ae86cd365d9c119be32
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553521"
---
# <a name="compiler-error-c2415"></a>Ошибка компилятора C2415

Недопустимый тип операнда

Код операции не использует операнды данного типа.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Код операции не поддерживает количество используемых операндов. Проверьте справочное руководство по языка ассемблера, чтобы определить правильное число операндов.

1. Новый процесс поддерживает инструкции с новыми типами. Настройка [/arch (минимальная архитектура ЦП)](../../build/reference/arch-minimum-cpu-architecture.md) параметр, чтобы использовать процессор более поздней.