---
title: Платформы Windows (CRT) | Документация Майкрософт
ms.custom: ''
ms.date: 02/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- CRT, compatibility
- backward compatibility [C++], C run-time libraries
- compatibility [C++], C run-time libraries
- MBCS [C++], Win32 platforms
- operating systems [C++]
- Unicode [C++], Win32 platforms
ms.assetid: 0aacaf45-6dc4-4908-bd52-57abac7b39f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f360cd075ac4a86c39f5c33391e974e62f481455
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613486"
---
# <a name="windows-platforms-crt"></a>Платформы Windows (CRT)

Библиотеки времени выполнения C для Visual Studio поддерживают текущие версии Windows и Windows Server, Windows 8, Windows Server 2012, Windows 7, Windows Server 2008 и Windows Vista, а также могут при необходимости поддерживать Windows XP с пакетом обновления 3 (SP3) для систем x86, Windows XP с пакетом обновления 2 (SP2) для x64 и Windows Server 2003 с пакетом обновления 2 (SP2) для x86 и x64. Все эти операционные системы поддерживают API для классических приложений Windows (Win32) и обеспечивают поддержку Юникода. Кроме того, любое приложение Win32 может использовать многобайтовую кодировку (MBCS).

> [!NOTE]
> Установка по умолчанию рабочей нагрузки **Разработка классических приложений на C++** в Visual Studio 2017 не включает поддержку разработки для Windows XP и Windows Server 2003. Чтобы использовать набор инструментов для платформы Windows XP, необходимо установить дополнительный компонент **Поддержка Windows XP для C++**.

## <a name="see-also"></a>См. также

[Совместимость](../c-runtime-library/compatibility.md)  
