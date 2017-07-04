# pokemonchallenge

**Please build this like you would an actual project you're working on. It
should be production-ready code that you're proud of. Also you need to publish
the code using MIT License and upload it in a public repo in Github.**


## Description
In the popular Pokémon game all moves and Pokémons have types(fire|water|rock|)
that determine how effective certain moves are against certain Pokémons.
So the a work by some very simple rules, a certain type can be super effective,
normal, not very effective or have no effect at all against another type. These translate respectively to 2x, 1x, 0.5x and 0x damage multiplication. If a
Pokémon has multiple types the effectiveness of a move against this Pokémon
will be the product of the effectiveness of the move to it's types.

---

## Formal Inputs & Outputs
### Input

The program should take the type of a move being used and the types of the Pokémon it is being used on.

**Example inputs**
``` fire -> grass
    fighting -> ice rock
    psychic -> poison dark
    water -> normal
    fire -> rock
```

### Output

The program should output the damage multiplier these types lead to.
**Example outputs**
```2x
   4x
   0x
   1x
   0.5x
```
---

### Notes/Hints

Since probably not every Dojo hacker is an avid Pokémon trainer that knows the
type effectiveness multipliers by heart here is a [Pokémon type chart].

---


## Bonus 1
Use the [Pokémon API] to calculate the output damage.

Like:
```http://pokeapi.co/api/v2/type/fire/
```
returns (skipped the long list)

```{  
    "name":"fire",
    "generation":{  
        "url":"http:\/\/pokeapi.co\/api\/v2\/generation\/1\/",
        "name":"generation-i"
    },
    "damage_relations":{  
        "half_damage_from":[  
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/7\/",
                "name":"bug"
            },
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/9\/",
                "name":"steel"
            },
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/10\/",
                "name":"fire"
            },
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/12\/",
                "name":"grass"
            },
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/15\/",
                "name":"ice"
            },
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/18\/",
                "name":"fairy"
            }
        ],
        "no_damage_from":[  

        ],
        "half_damage_to":[  
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/6\/",
                "name":"rock"
            },
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/10\/",
                "name":"fire"
            },
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/11\/",
                "name":"water"
            },
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/16\/",
                "name":"dragon"
            }
        ],
        "double_damage_from":[  
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/5\/",
                "name":"ground"
            },
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/6\/",
                "name":"rock"
            },
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/11\/",
                "name":"water"
            }
        ],
        "no_damage_to":[  

        ],
        "double_damage_to":[  
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/7\/",
                "name":"bug"
            },
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/9\/",
                "name":"steel"
            },
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/12\/",
                "name":"grass"
            },
            {  
                "url":"http:\/\/pokeapi.co\/api\/v2\/type\/15\/",
                "name":"ice"
            }
        ]
    },
    "game_indices":[  
       ...
    ],
    "move_damage_class":{  
        ...
    },
    "moves":[  
        ...
    ],
    "pokemon":[  
        ...
    ],
    "id":10,
    "names":[  
        ...
    ]
    }
```
If you parse this JSON, you can calculate the output, instead of hard coding it.

## Bonus 2
Deep further into the api and give the multiplier for folowing
```fire punch -> bulbasaur
   wrap -> onix
   surf -> dwegong
```

**Note: the API replaces a space with a hyphen (-)**

---

[Pokémon type chart]: https://pokemondb.net/type
[Pokémon API]: https://pokeapi.co/
