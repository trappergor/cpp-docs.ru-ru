---
title: '/експериментал: препроцессор (Включение режима соответствия препроцессора)'
description: 'Используйте параметр компилятора/експериментал: препроцессора, чтобы включить экспериментальную поддержку компилятора для стандартного соответствия препроцессору.'
ms.date: 09/10/2020
f1_keywords:
- preprocessor
- /experimental:preprocessor
helpviewer_keywords:
- preprocessor conformance
- /experimental:preprocessor
- Enable preprocessor conformance mode
ms.openlocfilehash: 9a98289434e7154d2ec8b8753d990876a8218acf
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042099"
---
# <a name="experimentalpreprocessor-enable-preprocessor-conformance-mode"></a>`/experimental:preprocessor` (Включить режим соответствия препроцессора)

Этот параметр является устаревшим начиная с Visual Studio 2019 версии 16,5, заменяя [`/Zc:preprocessor`](zc-preprocessor.md) параметром компилятора. **`/experimental:preprocessor`** включает экспериментальный препроцессор на основе маркеров, который более тесно соответствует стандартам C++ 11, включая функции препроцессора C99. Дополнительные сведения см. в разделе [компилятором MSVC New препроцессор Overview](../../preprocessor/preprocessor-experimental-overview.md).

## <a name="syntax"></a>Синтаксис

> **`/experimental:preprocessor`**\[**`-`**]

## <a name="remarks"></a>Комментарии

Используйте **`/experimental:preprocessor`** параметр компилятора, чтобы включить экспериментальный препроцессор. Можно использовать **`/experimental:preprocessor-`** параметр для явного указания традиционного препроцессора.

**`/experimental:preprocessor`** Параметр доступен начиная с Visual Studio 2017 версии 15,8. Начиная с Visual Studio 2019 версии 16,5, новый препроцессор завершен и доступен в [`/Zc:preprocessor`](zc-preprocessor.md) параметре компилятора.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Свойства конфигурации**  >  **C/C++**  >  **Командная строка** .

1. Измените свойство **Дополнительные параметры** , чтобы включить его *`/experimental:preprocessor`* , а затем нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также раздел

[/Zc (соответствие)](zc-conformance.md)
