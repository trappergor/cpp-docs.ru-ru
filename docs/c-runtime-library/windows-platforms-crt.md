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
ms.openlocfilehash: d53e8020bbb7649d78232025ef9c63c1dc868fee
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32409011"
---
# <a name="windows-platforms-crt"></a>Платформы Windows (CRT)

Библиотеки времени выполнения C для Visual Studio поддерживают текущие версии Windows и Windows Server, [!INCLUDE[win8](../build/reference/includes/win8_md.md)], [!INCLUDE[winserver8](../build/reference/includes/winserver8_md.md)], [!INCLUDE[win7](../build/includes/win7_md.md)], [!INCLUDE[winsvr08](../build/reference/includes/winsvr08_md.md)] и Windows Vista, а также могут при необходимости поддерживать [!INCLUDE[winxp](../build/includes/winxp_md.md)] с пакетом обновления 3 (SP3) для систем x86, [!INCLUDE[winxp](../build/includes/winxp_md.md)] с пакетом обновления 2 (SP2) для x64 и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] с пакетом обновления 2 (SP2) для x86 и x64. Все эти операционные системы поддерживают API для классических приложений Windows (Win32) и обеспечивают поддержку Юникода. Кроме того, любое приложение Win32 может использовать многобайтовую кодировку (MBCS).

> [!NOTE]
> Установка по умолчанию рабочей нагрузки **Разработка классических приложений на C++** в Visual Studio 2017 не включает поддержку разработки [!INCLUDE[winxp](../build/includes/winxp_md.md)] и [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Чтобы использовать набор инструментов для платформы Windows XP, необходимо установить дополнительный компонент **Поддержка Windows XP для C++**.

## <a name="see-also"></a>См. также

[Совместимость](../c-runtime-library/compatibility.md)  
