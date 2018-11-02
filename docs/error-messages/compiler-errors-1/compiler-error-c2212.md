---
title: Ошибка компилятора C2212
ms.date: 11/04/2016
f1_keywords:
- C2212
helpviewer_keywords:
- C2212
ms.assetid: 3fdab304-272c-4d07-bfd4-fad75170e536
ms.openlocfilehash: a632aaf9809cd306354320a21cb03b993d60a95f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496477"
---
# <a name="compiler-error-c2212"></a>Ошибка компилятора C2212

«Идентификатор»: __based недоступен для указателей на функции

Указатели на функции не могут объявляться как `__based`. Если вам нужны данные на основе кода, используйте `__declspec` ключевое слово или `data_seg` директивы pragma.