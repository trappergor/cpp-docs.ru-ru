---
title: Ошибка средств компоновщика LNK1223
ms.date: 11/04/2016
f1_keywords:
- LNK1223
helpviewer_keywords:
- LNK1223
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
ms.openlocfilehash: 331521c357389c2f7c1aa786969154a2b747ffe5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242829"
---
# <a name="linker-tools-error-lnk1223"></a>Ошибка средств компоновщика LNK1223

недопустимый или поврежденный файл: файл содержит недопустимые фрагменты .pdata

Для RISC-платформ, использующих pdata, эта ошибка возникнет, если компилятор выдаст фрагмент .pdata с несортированными записями.

Чтобы устранить эту проблему, попробуйте компилировать без [/GL (оптимизация всей программы)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md) включена. Также в некоторых случаях эта ошибка может возникнуть из-за пустого текста функций.