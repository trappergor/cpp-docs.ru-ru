---
title: '/Zc: препроцессор (Включение режима соответствия препроцессора)'
description: 'Используйте параметр компилятора/Zc: препроцессора, чтобы включить поддержку компилятора для стандартного соответствия препроцессору.'
ms.date: 09/10/2020
f1_keywords:
- preprocessor
- /Zc:preprocessor
helpviewer_keywords:
- preprocessor conformance
- /Zc:preprocessor
- Enable preprocessor conformance mode
ms.openlocfilehash: 356434e4892966b9a9304021dd5d8770dcc2f8b1
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90043179"
---
# <a name="zcpreprocessor-enable-preprocessor-conformance-mode"></a>`/Zc:preprocessor` (Включить режим соответствия препроцессора)

Этот параметр включает препроцессор на основе токенов, который соответствует стандартам C99 и C++ 11 и более поздних версий. Дополнительные сведения см. в разделе [компилятором MSVC New препроцессор Overview](../../preprocessor/preprocessor-experimental-overview.md).

## <a name="syntax"></a>Синтаксис

> **`/Zc:preprocessor`**[**-**]

## <a name="remarks"></a>Комментарии

**`/Zc:preprocessor`** Для включения препроцессора используйте параметр компилятора. Можно использовать **`/Zc:preprocessor-`** параметр, чтобы явно указать традиционный (не поддерживающий) препроцессор.

**`/Zc:preprocessor`** Параметр доступен начиная с Visual Studio 2019 версии 16,5. Более ранняя, неполная версия нового параметра препроцессора доступна в версиях Visual Studio, начиная с Visual Studio 2017 версии 15,8. Дополнительные сведения см. на веб-сайте [`/experimental:preprocessor`](experimental-preprocessor.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Свойства конфигурации**  >  **C/C++**  >  **Командная строка** .

1. Измените свойство **Дополнительные параметры** , чтобы включить его *`/Zc:preprocessor`* , а затем нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также раздел

[/Zc (соответствие)](zc-conformance.md)
