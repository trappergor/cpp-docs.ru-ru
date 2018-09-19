---
title: Ошибка средств компоновщика LNK1223 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1223
dev_langs:
- C++
helpviewer_keywords:
- LNK1223
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8639919c74559829367108b36d62594e2a83a91a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067997"
---
# <a name="linker-tools-error-lnk1223"></a>Ошибка средств компоновщика LNK1223

недопустимый или поврежденный файл: файл содержит недопустимые фрагменты .pdata

Для RISC-платформ, использующих pdata, эта ошибка возникнет, если компилятор выдаст фрагмент .pdata с несортированными записями.

Чтобы устранить эту проблему, попробуйте компилировать без [/GL (оптимизация всей программы)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md) включена. Также в некоторых случаях эта ошибка может возникнуть из-за пустого текста функций.