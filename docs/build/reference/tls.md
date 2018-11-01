---
title: /TLS
ms.date: 11/04/2016
f1_keywords:
- /TLS
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
ms.openlocfilehash: c125a6439e6cda2159a8bde2317528e667eaf310
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532643"
---
# <a name="tls"></a>/TLS

Отображает структуру IMAGE_TLS_DIRECTORY из исполняемого файла.

## <a name="remarks"></a>Примечания

/ TLS отображается полей структуры TLS, а также адресов функций обратного вызова TLS.

Если программа не использует локальное хранилище потока, ее образ не будет содержать структуру TLS.  См. в разделе [поток](../../cpp/thread.md) Дополнительные сведения.

IMAGE_TLS_DIRECTORY определяется в заголовке winnt.h.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](../../build/reference/dumpbin-options.md)