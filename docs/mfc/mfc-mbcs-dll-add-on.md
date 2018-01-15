---
title: "Надстройка DLL MFC MBCS | Документы Microsoft"
ms.custom: 
ms.date: 1/04/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MBCS
- MFC
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d6f134110ff95956cc37d6e038a680ff27cbc298
ms.sourcegitcommit: 56f6fce7d80e4f61d45752f4c8512e4ef0453e58
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2018
---
# <a name="mfc-mbcs-dll-add-on"></a>Надстройка DLL MBCS MFC

Поддержка MFC и его библиотек многобайтовой кодировки (MBCS), требуется дополнительный этап во время установки Visual Studio в Visual Studio 2013, 2015 г. и 2017 г.

**Visual Studio 2013**: по умолчанию библиотеки MFC, установленные в Visual Studio 2013 поддерживает только Юникод разработки. Требуется библиотек MBCS для построения проекта MFC в Visual Studio 2013 с **кодировки** свойство **использовать многобайтовую кодировку** или **не задано**. Загрузить DLL по [библиотека многобайтовые MFC для Visual Studio 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40770).

**Visual Studio 2015**: Юникода, так и библиотеки DLL MFC MBCS включены в компонентов программы установки Visual C++, но поддержка MFC не устанавливается по умолчанию. Visual C++ и MFC относятся к необязательным компонентам в программе установки Visual Studio. Чтобы убедиться в том, что компонент MFC установлен, в программе установки установите переключатель **Выборочная** и в разделе **Языки программирования**убедитесь, что выбраны пункты **Visual C++** и **Microsoft Foundation Classes для C++** . Если вы уже установили Visual Studio, при попытке создания проекта MFC вам будет предложено установить Visual C++ и (или) MFC.

**Visual Studio 2017 г**: В Юникоде и библиотеки DLL MFC MBCS устанавливаются вместе с **разработки настольных приложений с помощью C++** рабочей нагрузки, при выборе **поддерживают MFC и ATL** из  **Дополнительные компоненты** области. Если установку не включает эти компоненты, можно запустить установщик из **новые проекты** диалогового окна с помощью **откройте установщик Visual Studio** ссылку.

## <a name="see-also"></a>См. также

[Версии библиотек MFC](../mfc/mfc-library-versions.md)

