---
title: Ошибка средств компоновщика LNK1223
ms.date: 11/04/2016
f1_keywords:
- LNK1223
helpviewer_keywords:
- LNK1223
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
ms.openlocfilehash: 9c9d4c7224a7e65775354a86bd34fa9ea1b074af
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195036"
---
# <a name="linker-tools-error-lnk1223"></a>Ошибка средств компоновщика LNK1223

недопустимый или поврежденный файл: файл содержит недопустимые фрагменты .pdata

Для RISC-платформ, использующих pdata, эта ошибка возникнет, если компилятор выдаст фрагмент .pdata с несортированными записями.

Чтобы устранить эту проблему, попробуйте выполнить компиляцию без включения [/GL (оптимизация всей программы)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md) . Также в некоторых случаях эта ошибка может возникнуть из-за пустого текста функций.
