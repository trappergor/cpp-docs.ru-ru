---
title: '/експериментал: module (Включение поддержки модуля)'
description: 'Используйте параметр компилятора/експериментал: Module, чтобы включить экспериментальную поддержку компилятора для модулей.'
ms.date: 09/03/2019
f1_keywords:
- module
- /experimental:module
helpviewer_keywords:
- module
- /experimental:module
- Enable module support
ms.openlocfilehash: 82cce127ad5a2f87d11e4a653035bd80ea9f5001
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70294461"
---
# <a name="experimentalmodule-enable-module-support"></a>/експериментал: module (Включение поддержки модуля)

Включает экспериментальную поддержку компилятора для модулей, как указано в черновике C++ 20 Standard.

## <a name="syntax"></a>Синтаксис

> **/експериментал: module** [ **-** ]

## <a name="remarks"></a>Примечания

Включить поддержку экспериментальных модулей можно с помощью параметра компилятора **/експериментал: module** вместе с параметром [/std: c + + Latest](std-specify-language-standard-version.md) . Можно использовать **/експериментал: module-** для явного отключения поддержки модуля.

Этот параметр доступен начиная с Visual Studio 2015 с обновлением 1. Начиная с Visual Studio 2019 версии 16,2, черновые модули C++ 20 Standard не полностью реализованы в компиляторе Майкрософт C++ . С помощью функции "модули" можно создавать модули с одной секцией и импортировать модули стандартной библиотеки, предоставляемые корпорацией Майкрософт. Модуль и код, который его использует, должны быть скомпилированы с теми же параметрами компилятора.

Дополнительные сведения о модулях и их использовании и создании см. в разделе [Обзор модулей в C++ ](../../cpp/modules-cpp.md).

Ниже приведен пример параметров командной строки компилятора, используемых для создания модуля экспорта из исходного файла *ModuleName. икскс*:

```cmd
cl /EHsc /MD /experimental:module /module:export /module:name ModuleName /module:wrapper C:\Output\path\ModuleName.h /module:output C:\Output\path\ModuleName.ifc -c ModuleName.ixx
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите в раскрывающемся списке **Конфигурация** значение **все конфигурации**.

1. Выберите страницу свойств **конфигурации** > **C/C++**  > **Language** .

1. Измените свойство **включить C++ модули (экспериментальные)** и нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](zc-conformance.md)
