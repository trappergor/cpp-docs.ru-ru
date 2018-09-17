---
title: -Qpar-report (уровень отчетности автоматического Параллелизатора) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 847a93efc74c4e6111f49679219e1b26a70022f6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707520"
---
# <a name="qpar-report-auto-parallelizer-reporting-level"></a>/Qpar-report (уровень отчетности автоматического параллелизатора)

Включает функцию отчетности компилятора [автоматического Параллелизатора](../../parallel/auto-parallelization-and-auto-vectorization.md) и указывает уровень информационных сообщений для выходных данных во время компиляции.

## <a name="syntax"></a>Синтаксис

```
/Qpar-report:{1}{2}
```

## <a name="remarks"></a>Примечания

**/ Qpar-report: 1**<br/>
Выводит информационное сообщение для распараллеленных циклов.

**/ Qpar-report: 2**<br/>
Выводит информационное сообщение для распараллеленных циклов, а также для тех циклов, которые не были распараллелены, с указанием кода причины.

Сообщения выводятся в stdout. Если информационные сообщения отсутствуют, то либо код не содержит циклов, либо уровень отчетности не настроен для передачи отчетов о циклах, которые не удалось распараллелить. Дополнительные сведения о кодах причин и сообщениях см. в разделе [сообщения Векторизатора и Параллелизатора](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).

### <a name="to-set-the-qpar-report-compiler-option-in-visual-studio"></a>Настройка параметра компилятора /Qpar-report в Visual Studio

1. В области **Обозреватель решений**откройте контекстное меню для проекта и выберите пункт **Свойства**.

1. В **страницы свойств** диалогового **C/C++** выберите **командной строки**.

1. В **Дополнительные параметры** введите `/Qpar-report:1` или `/Qpar-report:2`.

### <a name="to-set-the-qpar-report-compiler-option-programmatically"></a>Настройка параметра компилятора /Qpar-report программным способом

- Используйте пример кода в <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры /Q (низкоуровневые операции)](../../build/reference/q-options-low-level-operations.md)
[параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[Параллельное программирование в машинном коде](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/04/12/auto-vectorizer-in-visual-studio-2012-overview/)