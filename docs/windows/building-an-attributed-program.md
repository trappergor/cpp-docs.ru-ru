---
title: Сборка Атрибутированной программы | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tlb files [C++]
- MIDL
- MIDL, linker output
- IDL files [C++]
- building type libraries and .idl files
- .tlb files [C++]
- .idl files [C++]
- type libraries, linker options for building
ms.assetid: 04997b5f-bf2c-46ec-b868-c4adebbef5f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2fc148478433106eabdb2bc57ef7bb6c91d13601
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315298"
---
# <a name="building-an-attributed-program"></a>Сборка атрибутированной программы

После помещения атрибутов Visual C++ в исходном коде, вы можете компилятор Visual C++ для создания файла библиотеки и .idl тип для вас. Компоновщик следующие параметры помогают построить файлы с расширением TLB и .idl:

- [/ IDLOUT](../build/reference/idlout-name-midl-output-files.md)

- [/ IGNOREIDL](../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)

- [/ MIDL](../build/reference/midl-specify-midl-command-line-options.md)

- [/ TLBOUT](../build/reference/tlbout-name-dot-tlb-file.md)

Некоторые проекты содержат несколько независимых .idl файлов. Они используются для создания двух или более TLB-файлы и их привязки в блоке ресурсов. Этот сценарий не поддерживается в Visual C++.

Кроме того компоновщик Visual C++ будет выводить все сведения атрибута, связанного с IDL, в единый файл MIDL. Будет невозможно создание двух библиотек типов в рамках одного проекта.

## <a name="see-also"></a>См. также

[Основные понятия](../windows/attributed-programming-concepts.md)