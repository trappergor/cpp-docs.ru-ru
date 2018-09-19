---
title: Предупреждение средств компоновщика LNK4205 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4205
dev_langs:
- C++
helpviewer_keywords:
- LNK4205
ms.assetid: d63b9d18-ef3c-4081-9d8d-93077dad13c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e76cef24436fc5ce3468a1c94be2d1a49733525a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105535"
---
# <a name="linker-tools-warning-lnk4205"></a>Предупреждение средств компоновщика LNK4205

«имя_файла» содержит текущей отладочной информации для ссылающегося модуля; компоновка объекта выполняется как при отсутствии отладочных данных

PDB-файл содержит устаревшие данные. Компоновщик продолжит компоновку объекта без отладочной информации. Можно перекомпилировать файл объекта с помощью [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) параметр.