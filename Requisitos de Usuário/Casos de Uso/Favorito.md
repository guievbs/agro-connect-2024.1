@startuml
left to right direction

actor "Usuário" as User

rectangle Sistema {
    User -down-> (Selecionar Item) : <size:10>Escolhe uma commodity ou notícia
    (Selecionar Item) -down-> (Marcar como Favorito) : <size:10>Adiciona o item à lista de favoritos
    
    rectangle "Marcação bem-sucedida" {
        (Marcar como Favorito) -down-> (Atualizar Favoritos) : <size:10>Salva o item na lista de favoritos
        (Atualizar Favoritos) -down-> User : <size:10>Notifica que o item foi marcado como favorito
    }
    
    rectangle "Erro ao marcar" {
        (Marcar como Favorito) -down-> (Notificar Erro) : <size:10>
        (Notificar Erro) -down-> User : <size:10>Informa que houve um erro ao tentar marcar o item como favorito
    }
}

@enduml
