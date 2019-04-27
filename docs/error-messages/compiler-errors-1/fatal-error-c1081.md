---
title: Неустранимая ошибка C1081
ms.date: 11/04/2016
f1_keywords:
- C1081
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
ms.openlocfilehash: f3c9f9bde5da7fb120accbb9a8d72e5715ab9d2b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62229423"
---
# <a name="fatal-error-c1081"></a>Неустранимая ошибка C1081

«символ»: слишком длинное имя файла

Длина пути файла превышает `_MAX_PATH` (определяемые STDLIB.h как 260 символов). Сократите имя файла.

При вызове CL.exe с коротким именем файла, компилятор может потребоваться создать полный путь. Например `cl -c myfile.cpp` может привести к созданию компилятором:

```
D:\<very-long-directory-path>\myfile.cpp
```