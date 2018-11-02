---
title: / APPCONTAINER (приложение UWP/Microsoft Store)
ms.date: 11/04/2016
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
ms.openlocfilehash: 306ffc7cda7cc6045b5decd6824fdc3848233824
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541327"
---
# <a name="appcontainer-microsoft-store-app"></a>/ APPCONTAINER (приложение Microsoft Store)

Указывает, создает ли компоновщик исполняемый образ, который должен запускаться в контейнере приложения.

## <a name="syntax"></a>Синтаксис

```
/APPCONTAINER[:NO]
```

## <a name="remarks"></a>Примечания

По умолчанию/appcontainer отключено.

Этот параметр изменяет исполняемый файл, чтобы указать, должна ли приложение выполняться в среде изоляции процессов appcontainer. Задайте параметр/appcontainer для приложения, который должен выполняться в среде appcontainer — например, для универсальной платформы Windows (UWP) или Windows Phone 8.x приложения. (Параметр задается автоматически в Visual Studio при создании приложения универсальной Windows на основе шаблона.) Для классического приложения укажите/appcontainer: no или просто опустив параметр.

Параметр/appcontainer впервые появился в Windows 8.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Разверните узел **Свойства конфигурации**.

1. Разверните **компоновщика** узла.

1. Выберите **командной строки** страницу свойств.

1. В **Дополнительные параметры**, введите `/APPCONTAINER` или `/APPCONTAINER:NO`.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)