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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383990"
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