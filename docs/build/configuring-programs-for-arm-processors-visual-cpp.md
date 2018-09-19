---
title: Настройка Visual C++ для процессоров ARM | Документация Майкрософт
ms.custom: ''
ms.date: 07/11/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 3d95f221-656a-480d-9651-9ad263895747
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ce0e7e1f7c0936daed0fa6a51f6e254403205e0
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714965"
---
# <a name="configure-visual-c-for-arm-processors"></a>Настройка Visual C++ для процессоров ARM

В этом разделе документации представлены сведения об использовании средств сборки Visual C++ для ориентации на оборудование ARM.

## <a name="in-this-section"></a>В этом разделе

[Обзор соглашений ABI ARM](../build/overview-of-arm-abi-conventions.md) описывает двоичный интерфейс приложений, используемых Windows на ARM для использования регистров, вызова соглашений и обработки исключений.

[Обзор соглашений ABI ARM64](../build/arm64-windows-abi-conventions.md) описывает двоичный интерфейс приложений, используемых Windows для ARM64 для использования регистров, вызова соглашений и обработки исключений.

[Visual C++ ARM затруднения](../build/common-visual-cpp-arm-migration-issues.md) элементов кода C++, описание, обычно предполагается, что можно переносить на другие архитектуры, однако их различные результаты для ARM, чем для x86 и x64.

[Обработка исключений ARM](../build/arm-exception-handling.md) описывает схему кодирования для очистки стека при структурированной обработке исключений в Windows на ARM.

[Обработка исключений ARM64](../build/arm64-exception-handling.md) описывает схему кодирования для очистки стека при структурированной обработке исключений в Windows на ARM64.

## <a name="related-sections"></a>Связанные разделы

[Встроенные функции ARM](../intrinsics/arm-intrinsics.md) Описывает встроенные функции компилятора для процессоров, использующих архитектуру ARM.
