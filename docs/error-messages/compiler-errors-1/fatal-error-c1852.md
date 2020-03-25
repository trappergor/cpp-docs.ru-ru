---
title: Неустранимая ошибка C1852
ms.date: 11/04/2016
f1_keywords:
- C1852
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
ms.openlocfilehash: 540febabc8f2947f11b58cf7eadee53d47f7bef3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202882"
---
# <a name="fatal-error-c1852"></a>Неустранимая ошибка C1852

"имя_файла" не является допустимым файлом предкомпилированного заголовка

Файл не является предкомпилированным заголовком.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Указан недопустимый файл с **/Yu** или **#pragma hdrstop**.

1. Если не указано иное, компилятор предполагает расширение файла PCH.
