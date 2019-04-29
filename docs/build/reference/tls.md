---
title: /TLS
ms.date: 11/04/2016
f1_keywords:
- /TLS
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
ms.openlocfilehash: 751c212398f3d309b1d31d204291fe3a0503cf06
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317267"
---
# <a name="tls"></a>/TLS

Отображает структуру IMAGE_TLS_DIRECTORY из исполняемого файла.

## <a name="remarks"></a>Примечания

/ TLS отображается полей структуры TLS, а также адресов функций обратного вызова TLS.

Если программа не использует локальное хранилище потока, ее образ не будет содержать структуру TLS.  См. в разделе [поток](../../cpp/thread.md) Дополнительные сведения.

IMAGE_TLS_DIRECTORY определяется в заголовке winnt.h.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](dumpbin-options.md)
