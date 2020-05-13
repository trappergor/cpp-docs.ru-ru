---
title: Неустранимая ошибка компилятора ресурсов RW1025
ms.date: 11/04/2016
f1_keywords:
- RW1025
helpviewer_keywords:
- RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
ms.openlocfilehash: 9b6697dff0a445cc342f30d08bd79822b02df7b8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172729"
---
# <a name="resource-compiler-fatal-error-rw1025"></a>Неустранимая ошибка компилятора ресурсов RW1025

Недостаточно памяти в куче

Проверьте наличие в памяти резидентного программного обеспечения, которое может занимать слишком много пространства. Используйте программу CHKDSK для определения объема используемой памяти.

При создании большого файла ресурсов разделите сценарий ресурсов на два файла. После создания двух RES файлов используйте командную строку MS-DOS, чтобы объединить их вместе:

```
copy first.res /b + second.res /b full.res
```
