---
title: Предупреждение компилятора (уровень 1) C4819 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4819
dev_langs:
- C++
helpviewer_keywords:
- C4819
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac468bc605c261b66f47fdf40efd1a01a5383d58
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074283"
---
# <a name="compiler-warning-level-1-c4819"></a>Предупреждение компилятора (уровень 1) C4819

Файл содержит символ, который нельзя отобразить с помощью текущей кодовой страницы (номер). Сохраните файл в формате Юникода, чтобы избежать потери данных.

Ошибка C4819 возникает, когда файл исходного кода ANSI компилируется в системе, кодовая страница которой не может отобразить все символы файла.

Чтобы устранить ошибку C4819, сохраните файл в формате Юникода. В Visual Studio, выберите **файл**, **Дополнительные параметры сохранения**. В **Дополнительные параметры сохранения** диалогового окна выберите кодировку, способную отобразить все символы в файле — например, UTF-8 и нажмите кнопку **ОК**.