---
title: "Надстройка DLL MFC MBCS | Документы Microsoft"
ms.custom: 
ms.date: 08/20/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MBCS
- MFC
ms.assetid: bebec0ff-e019-42ca-b5df-8c218ac5b54a
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 176ed47b4d6a799cf53d2a1cea8cb232f1c2c4aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-mbcs-dll-add-on"></a>Надстройка DLL MBCS MFC
 Для построения проекта MFC в Visual Studio 2015, в котором для свойства **Кодировка** установлено значение **Использовать многобайтовую кодировку** или **Не задано**, требуются многобайтовые библиотеки DLL.  

**Visual Studio 2013**: загрузка библиотеки DLL на [библиотека многобайтовые MFC для Visual Studio 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40770).

**Visual Studio 2015**: эту библиотеку DLL включается в компонентов программы установки Visual C++. Visual C++ и MFC относятся к необязательным компонентам в программе установки Visual Studio. Чтобы убедиться в том, что компонент MFC установлен, в программе установки установите переключатель **Выборочная** и в разделе **Языки программирования**убедитесь, что выбраны пункты **Visual C++** и **Microsoft Foundation Classes для C++** . Если вы уже установили Visual Studio, при попытке создания проекта MFC вам будет предложено установить Visual C++ и (или) MFC.  
  
**Visual Studio 2017 г**: эту библиотеку DLL устанавливается вместе с **для разработки классических приложений с помощью C++** рабочей нагрузки, при выборе **поддерживают MFC и ATL** из **дополнительных компонентов** области.

  
## <a name="see-also"></a>См. также  
 [Версии библиотек MFC](../mfc/mfc-library-versions.md)

