---
title: Ошибка средств компоновщика LNK1309 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1309
dev_langs:
- C++
helpviewer_keywords:
- LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ffecdc891a9fe0d1c17d6e36c87f5df10b449ec
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704102"
---
# <a name="linker-tools-error-lnk1309"></a>Ошибка средств компоновщика LNK1309

> *Тип 1* модуль обнаружен; недопустим с параметром коммутатора/CLRIMAGETYPE:*тип2*

## <a name="remarks"></a>Примечания

Тип образа среды CLR была запрошена с **/CLRIMAGETYPE** , но компоновщик не удалось создать образ этого типа, так как один или несколько модулей несовместимы с этим типом.

Например, вы увидите LNK1309 при указании **/CLRIMAGETYPE:safe** и передать модуль, построенный с **/CLR: pure**.

**/CLR: pure** и **/CLR: safe** параметров и поддержка библиотек компилятора признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017 г.

LNK1309 также возникает при попытке выполнить построение приложения с частичным доверием CLR чисто с помощью ptrustu [d] .lib. Сведения о создании приложения с частичным доверием см. в разделе [как: создать частично доверенного приложения путем удаления зависимостей для библиотеки DLL CRT](../../dotnet/create-a-partially-trusted-application.md).

Дополнительные сведения см. в разделе [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) и [/CLRIMAGETYPE (указать Type of CLR Image)](../../build/reference/clrimagetype-specify-type-of-clr-image.md).