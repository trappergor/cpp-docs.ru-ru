---
title: Формат изображения | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 3ca3654b-42fe-4253-9f2e-723644041aa0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e69d1a7c62d4e9c52cc628f30f94c346d83647f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715420"
---
# <a name="image-format"></a>Формат образа

Исполняемый образ имеет PE32 +. Исполняемые образы (DLL или exe) ограничены максимальным размером 2 гигабайта, поэтому относительный адресация с 32-разрядное смещение можно использовать для решения данных статическое изображение. Эти данные включают таблицы адресов импорта, строковые константы, глобальные статические данные и т. д.

## <a name="see-also"></a>См. также

[Программные соглашения для X64](../build/x64-software-conventions.md)