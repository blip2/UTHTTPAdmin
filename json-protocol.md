UTHTTPAdmin json protocol
===========

This file details the (proposed) json protocol for communicating with the server.

Getting Information
-----------

** Status **
Query:
    /server/status

Response:
    {
        "state": "GAMESTATE",
        "gamemode": "GAMEMODE",
        "map": "MAPNAME",
        "maplist": "LISTNAME",
        "playercount": "PLAYERCOUNT",
    }

** Players **
Query:
    /server/players

Response:
    {
        "players": {
            "0": {
                "id": "PLAYERID",
                "name": "PLAYERNAME",
                "team": "TEAM",
                "ping": "PING",
                "score": "SCORE",
                "kills": "KILLS",
                "deaths": "DEATHS",
                "suicides": "SUICIDES",
                "sprees": "SPREES",
                "multikills": "MULTIKILLS",
            },
            "1": {
                "id": "PLAYERID",
                "name": "PLAYERNAME",
                "team": "TEAM",
                "ping": "PING",
                "score": "SCORE",
                "kills": "KILLS",
                "deaths": "DEATHS",
                "suicides": "SUICIDES",
                "sprees": "SPREES",
                "multikills": "MULTIKILLS",
            }
        }
    }

** Map Lists **
Query:
    /server/maplist
    {
        "listname": "LISTNAME"
    }

LISTNAME is optional, not providing a value returns all lists.

Response:
    {
        "maplists": {
            "listname": "LISTNAME",
            "maps": {
                "0": "mapname1",
                "1": "mapname2",
                "2": "mapname3",
            }
        }
    }

Sending Commands
-----------

** Console Command **
Query:
    /server/console
    {
        "command": "CONSOLECMD",
    }

Response:
    {
        "response": "OK",
    }

** Kick Player **
Query:
    /server/kick
    {
        "player": "PLAYERID",
    }

Response:
    {
        "response": "OK",
    }

Getting Configuration Values
-----------

Setting Configuration Values
-----------