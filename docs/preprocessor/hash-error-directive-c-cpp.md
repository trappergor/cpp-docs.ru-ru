---
title: '#Ошибка директива (C/C++)'
ms.date: 11/04/2016
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
ms.openlocfilehash: c83fc7ef8135ee0cba37a956df47bcab0f796007
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447818"
---
# <a name="error-directive-cc"></a>Директива #error (C/C++)
**#Error** директивы выдает сообщение об ошибке, определяемый пользователем во время компиляции, а затем завершает компиляцию.

## <a name="syntax"></a>Синтаксис

```
#errortoken-string
```

## <a name="remarks"></a>Примечания

Сообщение об ошибке, этой директивой включает *строке токена* параметра. *Строке токена* параметр не подлежит расширению макроса. Эта директива наиболее полезна в ходе предварительной обработки и позволяет уведомлять разработчика о противоречиях в программе или о нарушении ограничений. В следующем примере демонстрируется обработка ошибки во время предварительной обработки.

```
#if !defined(__cplusplus)
#error C++ compiler required.
#endif
```

## <a name="see-also"></a>См. также

[Директивы препроцессора](../preprocessor/preprocessor-directives.md)