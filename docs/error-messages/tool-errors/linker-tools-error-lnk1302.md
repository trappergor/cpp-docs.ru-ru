---
title: Ошибка средств компоновщика LNK1302 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1302
dev_langs:
- C++
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3dc85b37d58e12602c02c2207c1f38bda9344e59
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045514"
---
# <a name="linker-tools-error-lnk1302"></a>Ошибка средств компоновщика LNK1302

поддерживается только компоновка безопасных .netmodule; не удалось связать файл .netmodule

.Netmodule (скомпилированные с использованием **/LN**) был передан компоновщику при попытке пользователя вызвать компоновку MSIL.  Модуля C++ является допустимым компоновка MSIL, если он скомпилирован с **/CLR: safe**.

Чтобы исправить эту ошибку, компиляцию с параметром **/CLR: safe** Включить компоновку MSIL или передать **/CLR** или **/CLR: pure** OBJ-файле компоновщику вместо модуля.

Дополнительные сведения см. в разделе .

- [/LN (создание модуля MSIL)](../../build/reference/ln-create-msil-module.md)

- [NETMODULE-файлы в качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md)