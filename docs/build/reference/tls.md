---
title: /TLS
ms.date: 11/04/2016
f1_keywords:
- /TLS
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
ms.openlocfilehash: 1760e94046a950f67d3c3fd7ef13aa40ca7de47a
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417792"
---
# <a name="tls"></a>/TLS

Отображает структуру IMAGE_TLS_DIRECTORY из исполняемого файла.

## <a name="remarks"></a>Примечания

/ TLS отображается полей структуры TLS, а также адресов функций обратного вызова TLS.

Если программа не использует локальное хранилище потока, ее образ не будет содержать структуру TLS.  См. в разделе [поток](../../cpp/thread.md) Дополнительные сведения.

IMAGE_TLS_DIRECTORY определяется в заголовке winnt.h.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](../../build/reference/dumpbin-options.md)
