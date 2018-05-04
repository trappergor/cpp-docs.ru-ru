---
title: / APPCONTAINER (приложение UWP или Microsoft Store) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ca1a3ed5adaada689d374eeb3e67bae6c989e0b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="appcontainer-microsoft-store-app"></a>/ APPCONTAINER (приложение магазина Microsoft)
Указывает, будет ли компоновщик создает исполняемый образ, который необходимо запустить в контейнере приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/APPCONTAINER[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию /APPCONTAINER — off.  
  
 Этот параметр изменяет исполняемый файл, чтобы указать, должно ли приложение выполняться в среде изоляции процесса контейнера приложений. Укажите /APPCONTAINER для приложения, которое должно выполняться в среде контейнера приложений — например, универсальной платформы Windows (UWP) или Windows Phone 8.x приложении. (Этот параметр задается автоматически в Visual Studio при создании универсального приложения Windows на основе шаблона.) Для классического приложения укажите /APPCONTAINER:NO или просто пропустите параметр.  
  
 Параметр /APPCONTAINER впервые появился в [!INCLUDE[win8](../../build/reference/includes/win8_md.md)].  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio  
  
1.  Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **компоновщика** узла.  
  
4.  Выберите **командной строки** страницу свойств.  
  
5.  В **Дополнительные параметры**, введите `/APPCONTAINER` или `/APPCONTAINER:NO`.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)