---
title: "Хранение строк в поставщике OLE DB | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "записи пользователя, редактирование"
ms.assetid: 36cb9635-067c-4cad-8f85-962f28026f6a
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Хранение строк в поставщике OLE DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

С помощью мастера поставщика ATL OLE DB в файле MyProviderRS.h создается используемая по умолчанию запись пользователя с именем `CWindowsFile`.  Для обработки двух строк измените запись `CWindowsFile` или добавьте собственную запись пользователя, как показано в следующем коде:  
  
```  
////////////////////////////////////////////////////////////////////////  
class CAgentMan:   
   public WIN32_FIND_DATA  
   DWORD dwBookmark;              // Add this  
   TCHAR szCommand[256];          // Add this  
   TCHAR szText[256];             // Add this  
   TCHAR szCommand2[256];         // Add this  
   TCHAR szText2[256];            // Add this  
  
{  
public:  
BEGIN_PROVIDER_COLUMN_MAP()  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command"), 1, 256, GUID_NULL, CAgentMan, szCommand)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text"), 2, 256, GUID_NULL, CAgentMan, szText)   
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Command2"), 3, 256, GUID_NULL, CAgentMan, szCommand2)  
   PROVIDER_COLUMN_ENTRY_STR(OLESTR("Text2"),4, 256, GUID_NULL, CAgentMan, szText2)  
END_PROVIDER_COLUMN_MAP()  
   bool operator==(const CAgentMan& am) // This is optional   
   {  
      return (lstrcmpi(cFileName, wf.cFileName) == 0);  
   }  
};  
```  
  
 Строки представляются членами данных `szCommand` и `szText`. Дополнительные столбцы при необходимости представляются членами данных `szCommand2` and `szText2`.  Для этого простого и доступного только для чтения поставщика не требуется член данных `dwBookmark`. Этот член данных используется позднее для добавления интерфейса `IRowsetLocate`. См. раздел [Повышение эффективности простого поставщика, предназначенного только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md).  Необязательный оператор `==` используется для сравнения экземпляров.  
  
 После выполнения этих действий можно выполнить компиляцию и запуск поставщика.  Чтобы выполнить тестирование поставщика, используйте объект\-получатель с соответствующими функциями.  Сведения о создании объекта\-получателя для тестирования см. в разделе [Реализация простых объектов\-получателей](../../data/oledb/implementing-a-simple-consumer.md).  Запустите тестовый объект\-получатель вместе с поставщиком.  При нажатии кнопки **Запустить** в диалоговом окне **Тестовый объект\-получатель**, убедитесь в том, чтобы строки, направляемые поставщиком объекту\-получателю, были правильными.  
  
 В случае успешного тестирования поставщика можно расширить его функциональные возможности, реализовав дополнительные интерфейсы.  Пример см. в разделе [Повышение эффективности простого поставщика, предназначенного только для чтения](../../data/oledb/enhancing-the-simple-read-only-provider.md).  
  
## См. также  
 [Реализация простого поставщика, предназначенного только для чтения](../../data/oledb/implementing-the-simple-read-only-provider.md)