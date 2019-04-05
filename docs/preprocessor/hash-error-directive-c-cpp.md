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
ms.openlocfilehash: dc229a8eae6938cba32787ecbec6a5aa6a17ab47
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037848"
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