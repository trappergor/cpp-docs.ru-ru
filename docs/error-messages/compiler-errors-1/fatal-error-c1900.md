---
title: Неустранимая ошибка C1900 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1900
dev_langs:
- C++
helpviewer_keywords:
- C1900
ms.assetid: 3aaa583b-4c1a-45de-aa34-527d806f2cb5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b2211b4243ddf44194959a263fd90ec1a615ea0a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220285"
---
# <a name="fatal-error-c1900"></a>Неустранимая ошибка C1900

> Несоответствие IL между "*средстве 1*«version»*Число1*«и»*средстве 2*«version»*число2*"

Средства, запускаемые на разных этапах работы компилятора, не совпадают. *Число1* и *число2* относятся к датам файлов. Например, на первом проходе внешний сегмент компилятора запускает (c1.dll), а на втором проходе внутренний сегмент компилятора запускает (c2.dll). Даты файлов должны совпадать.

Чтобы устранить эту проблему, убедитесь, что к Visual Studio применены все обновления. Если проблема сохранится, используйте **программы и компоненты** на панели управления Windows для восстановления или переустановки Visual Studio.