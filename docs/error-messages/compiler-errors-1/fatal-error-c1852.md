---
title: Неустранимая ошибка C1852
ms.date: 11/04/2016
f1_keywords:
- C1852
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
ms.openlocfilehash: 895c2fc988c9566f9e50b1ac1a18eb4dc1c6661a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165740"
---
# <a name="fatal-error-c1852"></a>Неустранимая ошибка C1852

"имя_файла" не является допустимым файлом предкомпилированного заголовка

Файл не является предкомпилированным заголовком.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Указан недопустимый файл с **/Yu** или **#pragma hdrstop**.

1. Если не указано иное, компилятор предполагает расширение файла PCH.