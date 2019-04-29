---
title: /APPCONTAINER
ms.date: 11/04/2016
f1_keywords:
- /APPCONTAINER
helpviewer_keywords:
- APPCONTAINER editbin option
- -APPCONTAINER editbin option
- /APPCONTAINER editbin option
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
ms.openlocfilehash: eb922a29b00fee63effae302505f25c98b04523e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274031"
---
# <a name="appcontainer"></a>/APPCONTAINER

Помечает исполняемый файл, который должен выполняться в контейнере приложения — например, Microsoft Store или универсальной Windows приложение.

```

/APPCONTAINER[:NO]
```

## <a name="remarks"></a>Примечания

Исполняемый файл, для которого задан параметр **/APPCONTAINER** , может выполняться только в контейнере приложения, то есть в среде изоляции процессов, которая была введена в Windows 8. Для приложений Microsoft Store и универсальной Windows этот параметр должен быть установлен.

## <a name="see-also"></a>См. также

[Параметры EDITBIN](editbin-options.md)<br/>
[Что такое универсальное приложение Windows?](/windows/uwp/get-started/universal-application-platform-guide)
