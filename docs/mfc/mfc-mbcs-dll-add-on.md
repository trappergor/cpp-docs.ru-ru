---
title: Надстройка DLL MFC MBCS | Документы Microsoft
ms.custom: ''
ms.date: 1/04/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MBCS
- MFC
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df6ecf03a5b1c92dc7e435fc014615db09422638
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-mbcs-dll-add-on"></a>Надстройка DLL MBCS MFC

Поддержка MFC и его библиотек многобайтовой кодировки (MBCS), требуется дополнительный этап во время установки Visual Studio в Visual Studio 2013, 2015 г. и 2017 г.

**Visual Studio 2013**: по умолчанию библиотеки MFC, установленные в Visual Studio 2013 поддерживает только Юникод разработки. Требуется библиотек MBCS для построения проекта MFC в Visual Studio 2013 с **кодировки** свойство **использовать многобайтовую кодировку** или **не задано**. Загрузить DLL по [библиотека многобайтовые MFC для Visual Studio 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40770).

**Visual Studio 2015**: Юникода, так и библиотеки DLL MFC MBCS включены в компонентов программы установки Visual C++, но поддержка MFC не устанавливается по умолчанию. Visual C++ и MFC относятся к необязательным компонентам в программе установки Visual Studio. Чтобы убедиться в том, что компонент MFC установлен, в программе установки установите переключатель **Выборочная** и в разделе **Языки программирования**убедитесь, что выбраны пункты **Visual C++** и **Microsoft Foundation Classes для C++** . Если вы уже установили Visual Studio, при попытке создания проекта MFC вам будет предложено установить Visual C++ и (или) MFC.

**Visual Studio 2017 г**: В Юникоде и библиотеки DLL MFC MBCS устанавливаются вместе с **разработки настольных приложений с помощью C++** рабочей нагрузки, при выборе **поддерживают MFC и ATL** из **необязательно Компоненты** области. Если установку не включает эти компоненты, можно запустить установщик из **новые проекты** диалогового окна с помощью **откройте установщик Visual Studio** ссылку.

## <a name="see-also"></a>См. также

[Версии библиотек MFC](../mfc/mfc-library-versions.md)

