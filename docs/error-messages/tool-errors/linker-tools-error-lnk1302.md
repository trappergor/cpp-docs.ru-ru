---
title: Ошибка средств компоновщика LNK1302
ms.date: 11/04/2016
f1_keywords:
- LNK1302
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
ms.openlocfilehash: c3b1117b31db4759b385943323a581da7a58f0c4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491082"
---
# <a name="linker-tools-error-lnk1302"></a>Ошибка средств компоновщика LNK1302

поддерживается только компоновка безопасных .netmodule; не удалось связать файл .netmodule

.Netmodule (скомпилированные с использованием **/LN**) был передан компоновщику при попытке пользователя вызвать компоновку MSIL.  Модуля C++ является допустимым компоновка MSIL, если он скомпилирован с **/CLR: safe**.

Чтобы исправить эту ошибку, компиляцию с параметром **/CLR: safe** Включить компоновку MSIL или передать **/CLR** или **/CLR: pure** OBJ-файле компоновщику вместо модуля.

Дополнительные сведения см. в разделе .

- [/LN (создание модуля MSIL)](../../build/reference/ln-create-msil-module.md)

- [NETMODULE-файлы в качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md)