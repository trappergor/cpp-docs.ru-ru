---
title: Ошибка компилятора C2170
ms.date: 11/04/2016
f1_keywords:
- C2170
helpviewer_keywords:
- C2170
ms.assetid: d5c663f0-2459-4e11-a8bf-a52b62f3c71d
ms.openlocfilehash: 828e5bbca0b796864ec8b364ee69c18a3b5eea00
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80206959"
---
# <a name="compiler-error-c2170"></a>Ошибка компилятора C2170

"идентификатор": не объявлен как функция, не может быть встроенным

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Директива pragma `intrinsic` используется для элемента, отличного от функции.

1. Директива pragma `intrinsic` используется для функции без встроенной формы.
