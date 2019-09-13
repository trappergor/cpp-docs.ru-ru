---
title: '#Директива error (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
ms.openlocfilehash: bfb5c18f20319e6e6d345f28d3e1850714334b71
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216124"
---
# <a name="error-directive-cc"></a>Директива #error (CC++/)

Директива **#error** выдает указанное пользователем сообщение об ошибке во время компиляции, а затем завершает компиляцию.

## <a name="syntax"></a>Синтаксис

> **#error** *Строка токена*

## <a name="remarks"></a>Примечания

Сообщение об ошибке, которое выдается этой директивой, включает параметр *строки токена* . Параметр *строки токена* не подлежит раскрытию макросов. Эта директива наиболее полезна во время предварительной обработки, чтобы уведомить разработчика о несогласованности программы или нарушение ограничения. В следующем примере демонстрируется обработка ошибки во время предварительной обработки.

```cpp
#if !defined(__cplusplus)
#error C++ compiler required.
#endif
```

## <a name="see-also"></a>См. также

[Директивы препроцессора](../preprocessor/preprocessor-directives.md)
