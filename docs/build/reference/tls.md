---
title: -TLS | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /TLS
dev_langs:
- C++
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78f485a783dbe8b5fe9a49ed3100754115bf50b8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714679"
---
# <a name="tls"></a>/TLS

Отображает структуру IMAGE_TLS_DIRECTORY из исполняемого файла.

## <a name="remarks"></a>Примечания

/ TLS отображается полей структуры TLS, а также адресов функций обратного вызова TLS.

Если программа не использует локальное хранилище потока, ее образ не будет содержать структуру TLS.  См. в разделе [поток](../../cpp/thread.md) Дополнительные сведения.

IMAGE_TLS_DIRECTORY определяется в заголовке winnt.h.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](../../build/reference/dumpbin-options.md)