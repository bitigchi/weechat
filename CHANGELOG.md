<!--
SPDX-FileCopyrightText: 2003-2025 Sébastien Helleu <flashcode@flashtux.org>

SPDX-License-Identifier: GPL-3.0-or-later
-->

# WeeChat ChangeLog

## Version 4.7.0 (2025-07-19)

### Changed

- **breaking:** core: fix buffer overflow in function utf8_next_char and return NULL for empty string
- **breaking:** core: fix integer overflow and return "unsigned long" in function util_version_number
- core: write configuration files on disk only if there are changes ([#2250](https://github.com/weechat/weechat/issues/2250))
- core: always enable partial completion for templates in option weechat.completion.partial_completion_templates, add option weechat.completion.partial_completion_auto_expand to expand word on new completion ([#2253](https://github.com/weechat/weechat/issues/2253))
- core: add script name in output of `/debug hooks <plugin>`
- relay/api: return HTTP error 405 (Method Not Allowed) when the method received is not allowed

### Added

- core: add support of specifier `%@` for UTC time in function util_strftimeval
- api: add function file_compare
- irc: add support of strikethrough text in IRC messages ([#2248](https://github.com/weechat/weechat/issues/2248))
- buflist: add variables `${number_zero}` and `${number_zero2}` (zero-padded buffer number)
- tests: add fuzz testing ([#1462](https://github.com/weechat/weechat/issues/1462))

### Fixed

- core: fix write of weechat.log to stdout with `weechat-headless --stdout` ([#2247](https://github.com/weechat/weechat/issues/2247))
- core: add refresh of window title on buffer switch, when option weechat.look.window_title is set
- core: consider all keys are safe in cursor context ([#2244](https://github.com/weechat/weechat/issues/2244))
- core: fix integer overflow with decimal numbers in calculation of expression
- core: fix integer overflow in base32 encoding/decoding
- core: fix buffer overflow in function util_parse_time
- core: fix buffer overflow in function eval_syntax_highlight_colorize
- core: fix buffer overflow in function eval_string_base_encode
- core: fix memory leak in function util_parse_delay
- irc: display nick changes and quit messages when option irc.look.ignore_tag_messages is enabled ([#2241](https://github.com/weechat/weechat/issues/2241))
- perl: fix build when multiplicity is not available ([#2243](https://github.com/weechat/weechat/issues/2243))
- relay/api: reject any invalid or unknown password hash algorithm in handshake resource
- relay/api: process HTTP request received as soon as a NULL char is received
- relay/weechat: fix empty buffers in client when WeeChat is running on Solaris/illumos
- build: fix build on Solaris/illumos ([#2251](https://github.com/weechat/weechat/issues/2251))

## Version 4.6.3 (2025-05-11)

### Fixed

- core: fix integer overflow with decimal numbers in calculation of expression
- core: fix integer overflow in base32 encoding/decoding
- core: fix integer overflow in function util_version_number
- core: fix buffer overflow in function util_parse_time
- core: fix buffer overflow in function eval_syntax_highlight_colorize
- core: fix buffer overflow in function eval_string_base_encode
- core: fix buffer overflow in function eval_string_range_chars
- core: fix memory leak in function util_parse_delay

## Version 4.6.2 (2025-04-18)

### Fixed

- core: fix write of weechat.log to stdout with `weechat-headless --stdout` ([#2247](https://github.com/weechat/weechat/issues/2247))
- core: add refresh of window title on buffer switch, when option weechat.look.window_title is set

## Version 4.6.1 (2025-04-09)

### Fixed

- core: consider all keys are safe in cursor context ([#2244](https://github.com/weechat/weechat/issues/2244))
- irc: display nick changes and quit messages when option irc.look.ignore_tag_messages is enabled ([#2241](https://github.com/weechat/weechat/issues/2241))
- perl: fix build when multiplicity is not available ([#2243](https://github.com/weechat/weechat/issues/2243))

## Version 4.6.0 (2025-03-23)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### Changed

- core: add option `-v` to display upgrades in command `/version`
- api: add property `keep_spaces_right` in function hook_set to keep trailing spaces in command arguments
- core, irc, alias, xfer: keep spaces at the end of some commands, where trailing spaces are important
- irc: add option `-connected` in command `/server list|listfull`
- buflist: apply option buflist.look.nick_prefix_empty also on private and list buffers
- xfer: compute speed and ETA with microsecond precision ([#665](https://github.com/weechat/weechat/issues/665))

### Added

- core: add command `/pipe`
- core: add option `whitespace` in command `/debug`, add options weechat.look.whitespace_char and weechat.look.tab_whitespace_char ([#947](https://github.com/weechat/weechat/issues/947))
- core: add option weechat.completion.nick_ignore_words ([#1143](https://github.com/weechat/weechat/issues/1143))
- spell: add CMake options ASPELL_DICT_DIR and ENCHANT_MYSPELL_DICT_DIR to override dictionaries locations ([#1174](https://github.com/weechat/weechat/issues/1174))
- api: add function completion_set
- relay/api: add resource `POST /api/completion` ([#2207](https://github.com/weechat/weechat/issues/2207))
- relay/api: add default key `Alt`+`Ctrl`+`l` (L) to toggle between remote and local commands on remote buffers, add option `togglecmd` in command `/remote`, add options relay.api.remote_input_cmd_local and relay.api.remote_input_cmd_remote ([#2148](https://github.com/weechat/weechat/issues/2148))

### Fixed

- relay: fix crash after `/upgrade` when relay clients are connected
- core: save configuration files as UTF-8 when the locale is wrong
- api: fix creation of empty buffer in function infolist_new_var_buffer
- core: fix build with gcc 15 ([#2229](https://github.com/weechat/weechat/issues/2229), [#2230](https://github.com/weechat/weechat/issues/2230))
- core: fix detection of dl library ([#2218](https://github.com/weechat/weechat/issues/2218))
- logger: fix path displayed when the logs directory can not be created
- perl: fix build with Perl < 5.7.29 ([#2219](https://github.com/weechat/weechat/issues/2219), [#2220](https://github.com/weechat/weechat/issues/2220))
- python: enable subinterpreters ([#2222](https://github.com/weechat/weechat/issues/2222))

## Version 4.5.2 (2025-02-20)

### Fixed

- core: fix build with gcc 15 ([#2229](https://github.com/weechat/weechat/issues/2229), [#2230](https://github.com/weechat/weechat/issues/2230))

## Version 4.5.1 (2024-12-23)

### Fixed

- relay: fix crash after `/upgrade` when relay clients are connected
- api: fix creation of empty buffer in function infolist_new_var_buffer
- core: fix detection of dl library ([#2218](https://github.com/weechat/weechat/issues/2218))
- logger: fix path displayed when the logs directory can not be created
- perl: fix build with Perl < 5.7.29 ([#2219](https://github.com/weechat/weechat/issues/2219), [#2220](https://github.com/weechat/weechat/issues/2220))

## Version 4.5.0 (2024-12-15)

### Changed

- api: return the buffer input callback return code in functions command and command_options
- api: add special value `-` (hyphen-minus) in options of function command_options to prevent execution of commands
- api: add property `hotlist_conditions` in function buffer_set
- api: add support of flags in functions hook_signal_send and hook_hsignal_send
- relay/api: allow array with multiple requests in websocket frame received from client
- relay/api: support passing authentication in sub protocol header ([#2205](https://github.com/weechat/weechat/issues/2205))
- relay/api: combine request headers with the same name ([#2206](https://github.com/weechat/weechat/issues/2206))
- core, plugins: simplify help on parameters that can be repeated in commands
- core: add optional hook types in command `/debug hooks`
- php: add detection of PHP 8.3 and 8.4
- ruby: fix detection of Ruby on macOS 14, require CMake ≥ 3.18 ([#1156](https://github.com/weechat/weechat/issues/1156))
- build: require Curl ≥ 7.47.0 ([#2195](https://github.com/weechat/weechat/issues/2195))
- build: require GnuTLS ≥ 3.3.0 ([#2193](https://github.com/weechat/weechat/issues/2193))

### Added

- relay: display connection status in input prompt of remote buffers, if not connected or if fetching data from remote
- irc: add option irc.look.notice_nicks_disable_notify
- irc: add infos "irc_ptr_server", "irc_ptr_channel" and "irc_ptr_nick"

### Fixed

- core, plugins: fix integer overflow in loops ([#2178](https://github.com/weechat/weechat/issues/2178), [CVE-2024-46613](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2024-46613))
- irc: decode IRC colors only when displaying messages in buffer, store nick info with IRC colors (host, account, real name)
- irc: do not strip trailing spaces from incoming IRC messages
- irc: fix crash on /list buffer when a filter is set ([#2197](https://github.com/weechat/weechat/issues/2197))
- script: fix crash on /script buffer when a filter is set ([#2214](https://github.com/weechat/weechat/issues/2214), [#2215](https://github.com/weechat/weechat/issues/2215))
- exec: fix unexpected execution of command with `/exec -o` when the command starts with two command chars ([#2199](https://github.com/weechat/weechat/issues/2199))
- relay/api: fix empty nicklist in remote buffers after connection or reconnection
- relay/api: reply HTTP 400 (Bad Request) when the body received is not a dict in websocket data
- core: fix too many sorts of hotlist when buffers are moved ([#2097](https://github.com/weechat/weechat/issues/2097))
- core: always send the signal "buffer_switch", even when the buffer is opening ([#2198](https://github.com/weechat/weechat/issues/2198))
- core, plugins: abort upgrade immediately if any upgrade file fails to be written
- core: reload all plugins with command `/plugin reload *`
- relay, xfer: fix letters with actions displayed on top of buffer
- perl: fix crash when unloading Perl scripts with Perl 5.38 ([#2209](https://github.com/weechat/weechat/issues/2209), [#2213](https://github.com/weechat/weechat/issues/2213))
- lua: fix compilation on Fedora with Lua < 5.2.0 ([#2173](https://github.com/weechat/weechat/issues/2173), [#2174](https://github.com/weechat/weechat/issues/2174))
- core: fix build on Darwin ([#2216](https://github.com/weechat/weechat/issues/2216))
- core: fix build on Android ([#2180](https://github.com/weechat/weechat/issues/2180))

## Version 4.4.4 (2024-11-30)

### Fixed

- script: fix crash on /script buffer when a filter is set ([#2214](https://github.com/weechat/weechat/issues/2214), [#2215](https://github.com/weechat/weechat/issues/2215))
- core: fix too many sorts of hotlist when buffers are moved ([#2097](https://github.com/weechat/weechat/issues/2097))
- relay, xfer: fix letters with actions displayed on top of buffer
- build: fix detection of Ruby on macOS 14, require CMake ≥ 3.18 ([#1156](https://github.com/weechat/weechat/issues/1156))
- perl: fix crash when unloading Perl scripts with Perl 5.38 ([#2209](https://github.com/weechat/weechat/issues/2209), [#2213](https://github.com/weechat/weechat/issues/2213))

## Version 4.4.3 (2024-10-30)

### Fixed

- irc: fix crash on /list buffer when a filter is set ([#2197](https://github.com/weechat/weechat/issues/2197))
- core: always send the signal "buffer_switch", even when the buffer is opening ([#2198](https://github.com/weechat/weechat/issues/2198))
- core: fix build on Android ([#2180](https://github.com/weechat/weechat/issues/2180))

## Version 4.4.2 (2024-09-08)

### Fixed

- core, plugins: fix integer overflow in loops ([#2178](https://github.com/weechat/weechat/issues/2178), [CVE-2024-46613](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2024-46613))

## Version 4.4.1 (2024-08-19)

### Fixed

- lua: fix compilation on Fedora with Lua < 5.2.0 ([#2173](https://github.com/weechat/weechat/issues/2173), [#2174](https://github.com/weechat/weechat/issues/2174))

## Version 4.4.0 (2024-08-17)

### Changed

- **breaking:** relay/api: flatten JSON event object sent to clients, always set "body_type" and "body" (null if there is no body) in websocket frame, add body types `buffers` and `lines` (array), add field "request_id" in websocket frame (request and response)
- **breaking:** core, plugins: force "short_name" in buffers to non-empty value (name by default), remove buffer property "short_name_is_set"
- **breaking:** alias: display an error with `/alias add` or `/alias addcompletion` when the alias already exists, add options `addreplace` and `addreplacecompletion` in command `/alias` ([#2095](https://github.com/weechat/weechat/issues/2095))
- **breaking:** irc: rename parameter `-re` to `-raw` in command `/list` ([#2124](https://github.com/weechat/weechat/issues/2124))
- **breaking:** api: add constants for IPv6 and allow force of IPv6 in function hook_connect ([#2164](https://github.com/weechat/weechat/issues/2164))
- **breaking:** irc: convert server option `ipv6` from boolean to enum (disable, auto, force) ([#2164](https://github.com/weechat/weechat/issues/2164))
- **breaking:** core: convert proxy option `ipv6` from boolean to enum (disable, auto, force), set option to `auto` by default when creating a new proxy ([#2164](https://github.com/weechat/weechat/issues/2164))
- core: add option `addreplace` in commands `/bar` and `/proxy` ([#2095](https://github.com/weechat/weechat/issues/2095))
- irc: add option `addreplace` in commands `/ignore`, `/notify` and `/server` ([#2095](https://github.com/weechat/weechat/issues/2095))
- relay: add option `addreplace` in commands `/relay` and `/remote` ([#2095](https://github.com/weechat/weechat/issues/2095))
- core: allow buffer id in commands `/buffer` and `/print`, in addition to number and name
- core: allow mask in command `/item refresh`
- relay: enable websocket extension "permessage-deflate" with "api" relay only ([#1549](https://github.com/weechat/weechat/issues/1549))
- relay/api: add automatic reconnection to remote, add remote option "autoreconnect_delay" in remote, add options relay.api.remote_autoreconnect_delay_growing and relay.api.remote_autoreconnect_delay_max ([#2166](https://github.com/weechat/weechat/issues/2166))
- relay/api: automatically reconnect to remotes with "autoconnect" enabled after `/upgrade`
- relay/api: add field "hidden" in GET /api/buffers, add support of hidden buffers in remote client ([#2159](https://github.com/weechat/weechat/issues/2159))
- relay/api: add field "time_displayed" in GET /api/buffers, add support of time displayed in remote client buffers
- relay/weechat: add line id in buffer lines sent to clients
- relay: display connection status in output of commands `/remote list` and `/remote listfull`
- relay: add option `reconnect` in command `/remote` ([#2160](https://github.com/weechat/weechat/issues/2160))
- irc: add support of message 569 (whois, connecting from) ([#2162](https://github.com/weechat/weechat/issues/2162))
- api: allow NULL value for key in hashtable
- doc: rename doc "weechat_relay_protocol" to "weechat_relay_weechat"

### Added

- core: add command line option `--build-info` / `-i` to display information about build options ([#449](https://github.com/weechat/weechat/issues/449))
- irc: add option `-export` in command `/list`, add option irc.look.list_buffer_format_export
- relay: add option relay.network.websocket_permessage_deflate ([#1549](https://github.com/weechat/weechat/issues/1549))
- relay: add option relay.look.raw_messages_max_length ([#2122](https://github.com/weechat/weechat/issues/2122))
- relay: add infos "relay_api_version" and "relay_api_version_number"
- relay/api: add event "quit", sent to clients when WeeChat is quitting ([#2168](https://github.com/weechat/weechat/issues/2168))
- script: add info "script_info"
- core: add hdata count in evaluation of expressions with `hdata_count:name[list]` or `hdata_count:name[pointer]`
- core: add info "window" ([#2141](https://github.com/weechat/weechat/issues/2141))
- core: add completion "bars_items"
- core: add signals "layout_buffers_applied" and "layout_windows_applied" ([#2167](https://github.com/weechat/weechat/issues/2167))
- core: add signal "buffer_time_for_each_line_changed"
- api, relay: send new signal "buffer_line_data_changed" when a line is updated in a buffer via hdata, send event "buffer_line_data_changed" to clients of "api" and "weechat" protocols
- api: add hashtable type "longlong"
- api: add function line_search_by_id
- doc: add doc on "api" relay

### Fixed

- python: fix crash on quit with Python 3.12 ([#2046](https://github.com/weechat/weechat/issues/2046), [#2126](https://github.com/weechat/weechat/issues/2126))
- core: fix crash when deleting a bar that has no items ([#2138](https://github.com/weechat/weechat/issues/2138))
- relay/api: fix crash when sending data to a remote buffer when the remote has been deleted ([#2157](https://github.com/weechat/weechat/issues/2157))
- irc, xfer: fix display of input prompt in IRC private buffers and DCC chat buffers ([#2128](https://github.com/weechat/weechat/issues/2128))
- irc: fix send of split messages when server option "anti_flood" set to 0 ([#2172](https://github.com/weechat/weechat/issues/2172))
- core: fix generation of TOTP on FreeBSD ([#2171](https://github.com/weechat/weechat/issues/2171))
- core: apply buffer properties (options weechat.buffer.*) when a buffer name is changed
- irc: fix property "short_name" of channel buffer when the joined channel has a different case than the `/join` command
- irc: close /list buffer when the server buffer is closed ([#2121](https://github.com/weechat/weechat/issues/2121))
- irc: clear /list buffer when disconnecting from server ([#2133](https://github.com/weechat/weechat/issues/2133))
- irc: display an explicit message on /list buffer when the list of channels is empty ([#2133](https://github.com/weechat/weechat/issues/2133))
- xfer: fix send of data on the DCC chat buffer after `/upgrade` if the buffer was opened before the upgrade ([#2092](https://github.com/weechat/weechat/issues/2092))
- core: fix refresh of bar item "scroll" in root bar after `/buffer clear` ([#590](https://github.com/weechat/weechat/issues/590))
- core, plugins: return "0x0" instead of "(nil)" for pointers formatted in strings
- core: send signal "buffer_moved" for all buffers affected by merge/unmerge
- ruby: fix builtin functions not available ([#2109](https://github.com/weechat/weechat/issues/2109))
- php: fix return value of function hdata_longlong
- tcl: fix return value of function hdata_longlong ([#2119](https://github.com/weechat/weechat/issues/2119))
- relay/api: fix connection to remote using an IPv6 address with square brackets ([#2156](https://github.com/weechat/weechat/issues/2156))
- relay/api: allow clients without authentication when no relay password is defined and option relay.network.allow_empty_password is on ([#2158](https://github.com/weechat/weechat/issues/2158))
- relay/api: fix connection to remote without password ([#2158](https://github.com/weechat/weechat/issues/2158))
- relay/api: fix timezone of dates sent to clients ([#2151](https://github.com/weechat/weechat/issues/2151))
- relay/api: clear lines and nicklist on all remote buffers upon successful connection to the remote ([#2161](https://github.com/weechat/weechat/issues/2161))
- relay/api: fix buffers synchronization with existing buffers that have been renamed on remote in the meanwhile ([#2169](https://github.com/weechat/weechat/issues/2169))
- relay/api: do not reset input text on existing buffers when reconnecting to the remote
- relay/api: close obsolete buffers when reconnecting to the remote
- relay/api: fix "body_type" returned when lines or nicks of a buffer are requested
- relay/api: fix read of one buffer line
- relay/api: automatically disconnect when the command `/upgrade` is executed on the remote
- relay/api: fix send of data to remote after command `/upgrade` executed in the remote client
- relay/api: disconnect from remote in case of error when sending data
- relay/api: disconnect cleanly when the remote is quitting ([#2168](https://github.com/weechat/weechat/issues/2168))
- relay: fix websocket permessage-deflate extension when the client doesn't send the max window bits parameters ([#1549](https://github.com/weechat/weechat/issues/1549))
- relay: fix allocation and reinit of field "client_context_takeover" in websocket deflate structure ([#1549](https://github.com/weechat/weechat/issues/1549))
- spell: improve error displayed when a word cannot be added to the dictionary ([#2144](https://github.com/weechat/weechat/issues/2144))
- core: fix completion of command `/item refresh`
- lua: remote string "Lua" from Lua version in output of `/debug libs`
- core: fix detection of libgcrypt ≥ 1.11 ([debian #1071960](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1071960))
- core, relay: fix include directory of libcjson and libzstd
- tests: fix relay tests on s390x ([#2118](https://github.com/weechat/weechat/issues/2118))
- tests: fix check of php plugin ([#2117](https://github.com/weechat/weechat/issues/2117))
- tests: fix compilation of tests on Fedora 40 ([#2116](https://github.com/weechat/weechat/issues/2116))
- tests: fix compilation of tests on Rocky 9.4

## Version 4.3.6 (2024-08-15)

### Fixed

- core: fix generation of TOTP on FreeBSD ([#2171](https://github.com/weechat/weechat/issues/2171))
- relay/api: fix crash when sending data to a remote buffer when the remote has been deleted ([#2157](https://github.com/weechat/weechat/issues/2157))
- relay/api: fix timezone of dates sent to clients ([#2151](https://github.com/weechat/weechat/issues/2151))

## Version 4.3.5 (2024-07-16)

### Fixed

- ruby: fix crash in plugin initialization ([#2163](https://github.com/weechat/weechat/issues/2163))

## Version 4.3.4 (2024-07-03)

### Fixed

- python: fix crash on quit with Python 3.12 ([#2046](https://github.com/weechat/weechat/issues/2046), [#2126](https://github.com/weechat/weechat/issues/2126))
- core: fix crash when deleting a bar that has no items ([#2138](https://github.com/weechat/weechat/issues/2138))
- ruby: fix builtin functions not available ([#2109](https://github.com/weechat/weechat/issues/2109))
- relay/api: fix "body_type" returned when lines or nicks of a buffer are requested

## Version 4.3.3 (2024-06-22)

### Fixed

- core, plugins: return "0x0" instead of "(nil)" for pointers formatted in strings

## Version 4.3.2 (2024-06-06)

### Changed

- relay: enable websocket extension "permessage-deflate" with "api" relay only ([#1549](https://github.com/weechat/weechat/issues/1549))

### Added

- relay: add option relay.look.raw_messages_max_length ([#2122](https://github.com/weechat/weechat/issues/2122))

### Fixed

- irc, xfer: fix display of input prompt in IRC private buffers and DCC chat buffers ([#2128](https://github.com/weechat/weechat/issues/2128))
- irc: don't return pointer to irc server if the channel or nick is not found in info "irc_buffer"
- relay: fix websocket permessage-deflate extension when the client doesn't send the max window bits parameters ([#1549](https://github.com/weechat/weechat/issues/1549))
- relay: fix allocation and reinit of field "client_context_takeover" in websocket deflate structure ([#1549](https://github.com/weechat/weechat/issues/1549))

## Version 4.3.1 (2024-05-31)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### Fixed

- irc: don't return pointer to irc server if the channel or nick is not found in info "irc_buffer"
- irc: close /list buffer when the server buffer is closed ([#2121](https://github.com/weechat/weechat/issues/2121))
- xfer: fix send of data on the DCC chat buffer after `/upgrade` if the buffer was opened before the upgrade ([#2092](https://github.com/weechat/weechat/issues/2092))
- php: fix return value of function hdata_longlong
- tcl: fix return value of function hdata_longlong ([#2119](https://github.com/weechat/weechat/issues/2119))
- core: fix detection of libgcrypt ≥ 1.11 ([debian #1071960](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1071960))
- core, relay: fix include directory of libcjson and libzstd
- tests: fix relay tests on s390x ([#2118](https://github.com/weechat/weechat/issues/2118))
- tests: fix check of php plugin ([#2117](https://github.com/weechat/weechat/issues/2117))
- tests: fix compilation of tests on Fedora 40 ([#2116](https://github.com/weechat/weechat/issues/2116))
- tests: fix compilation of tests on Rocky 9.4

## Version 4.3.0 (2024-05-26)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### Changed

- **breaking:** irc: add server option "autojoin_delay" (delay before autojoin), use option "command_delay" before execution of the command ([#862](https://github.com/weechat/weechat/issues/862))
- **breaking:** irc: rename option irc.color.item_channel_modes to weechat.color.status_modes
- **breaking:** irc: add option `-all` in command `/allchan`, do not execute command on parted channels by default ([#2085](https://github.com/weechat/weechat/issues/2085))
- **breaking:** relay: rename option relay.weechat.commands to relay.network.commands and change default to `*,!quit` ([#2066](https://github.com/weechat/weechat/issues/2066))
- **breaking:** relay: change option type relay.look.auto_open_buffer to string ([#2066](https://github.com/weechat/weechat/issues/2066))
- **breaking:** core: add buffer properties "input_prompt" and "modes", used to display bar items ([#2066](https://github.com/weechat/weechat/issues/2066))
- **breaking:** core: add bar item "lag" to display lag on relay remote buffers ([#2066](https://github.com/weechat/weechat/issues/2066))
- **breaking:** core: send signal "buffer_line_added" on buffers with free content
- **breaking:** core: convert option weechat.look.hotlist_sort to a list of fields ([#2097](https://github.com/weechat/weechat/issues/2097))
- **breaking:** core: rename variables with creation time in hdata "hotlist": "creation_time.tv_sec" to "time" and "creation_time.tv_usec" to "time_usec"
- **breaking:** api: return `-1` or `1` if one input string is NULL and not the other in string comparison functions
- **breaking:** api: use whole replacement string instead of first char in function string_remove_color
- core: use nick offline color for nick in action message ([#446](https://github.com/weechat/weechat/issues/446))
- core: display a specific message when the value of option is unchanged after `/set` command
- core: add variable `${highlight}` in option weechat.look.buffer_time_format ([#2079](https://github.com/weechat/weechat/issues/2079))
- core: reintroduce help on the variables and operators in `/help eval` ([#2005](https://github.com/weechat/weechat/issues/2005))
- core: allow case-insensitive search of partial buffer name with `(?i)name` in command `/buffer`
- core: use function util_strftimeval in evaluation of expression `date:xxx`
- fset: allow filename starting with "~" in command `/fset -export`
- irc: store lag in channel and private buffers (local variable "lag"), in addition to the server buffer
- irc: allow range in commands `/unban` and `/unquiet` ([#2113](https://github.com/weechat/weechat/issues/2113))
- tcl: add support of Tcl 9.0 ([#2075](https://github.com/weechat/weechat/issues/2075))

### Added

- relay: add "api" protocol (HTTP REST API), add options relay.look.display_clients, relay.api.remote_get_lines and relay.network.time_window ([#2066](https://github.com/weechat/weechat/issues/2066))
- relay: add command `/remote` to connect to remote WeeChat relay servers ([#2066](https://github.com/weechat/weechat/issues/2066))
- relay: add support of websocket extension "permessage-deflate" ([#1549](https://github.com/weechat/weechat/issues/1549))
- core, api: add unique identifier "id" in buffer and nicklist (group and nick), add function "hdata_longlong", allow search by buffer id in function buffer_search, allow search by group and nick id in functions nicklist_search_group and nicklist_search_nick ([#2081](https://github.com/weechat/weechat/issues/2081))
- core: add support of XDG "state" directory ([#2106](https://github.com/weechat/weechat/issues/2106), [#1747](https://github.com/weechat/weechat/issues/1747))
- core: add support of SGR mouse events ([#2082](https://github.com/weechat/weechat/issues/2082))
- fset: add option `-import` in command `/fset`
- core: add option `-s` in command `/command` to execute multiple commands separated by semicolons
- core: add option `malloc_trim` in command `/sys`
- core: add option weechat.look.config_permissions ([#2057](https://github.com/weechat/weechat/issues/2057))
- core: add option weechat.look.highlight_prefix ([#2079](https://github.com/weechat/weechat/issues/2079))
- core: add option weechat.completion.case_sensitive
- api: add functions config_option_get_{string|pointer} and config_{boolean|integer|string|color|enum}_inherited in scripting API
- api: add modifier "color_decode" to decode WeeChat colors with a replacement string
- api: add support of base64url in encode/decode functions
- api: add support of specifier `%!` for timestamp in function util_strftimeval
- api: add info "plugin_loaded"
- script: add option `enable` in command `/script`
- script: add info "script_loaded"

### Fixed

- core: fix conversion of WeeChat colors to ANSI colors: "default", "bar_fg", "bar_bg", "bar_delim"
- core: fix recursive search of group in nicklist
- core: use nick offline highlight color for prefix of action message when the nick is offline with a highlight
- core: add missing hdata name "buffer" in hdata "hotlist"
- core: fix reset to initial scroll position after search of text in buffer ([#2093](https://github.com/weechat/weechat/issues/2093))
- core: add missing mouse events "alt-ctrl-button2" and "alt-ctrl-button3"
- core: remove trailing directory separators in home directories ([#2070](https://github.com/weechat/weechat/issues/2070))
- exec: remove trailing space on buffers with free content when line numbers are not displayed
- exec: add missing exec tags in lines of buffers with free content ([#2086](https://github.com/weechat/weechat/issues/2086))
- irc: fix crash in split of IRC message containing a newline if the server is not given
- irc: fix display of reply for CTCP request received on a channel when capability echo-message is enabled
- irc: display CTCP reply to a nick in server buffer instead of channel
- irc: add missing tags on self action messages when capability echo-message is enabled ([#2074](https://github.com/weechat/weechat/issues/2074))
- irc: don't strip monospace color code 0x11 from incoming messages ([#2073](https://github.com/weechat/weechat/issues/2073))
- irc: fix random date displayed when a received message contains tags but no "time" ([#2064](https://github.com/weechat/weechat/issues/2064))
- lua: fix freeze on call to "debug.debug" ([#1906](https://github.com/weechat/weechat/issues/1906), [#1907](https://github.com/weechat/weechat/issues/1907))
- python: fix truncation of unsigned long long integer returned by function string_parse_size
- relay: set the last IRC client disconnection time only after a successful connection ([#2103](https://github.com/weechat/weechat/issues/2103))
- script: always display list of scripts when searching scripts with `/script search` ([#2077](https://github.com/weechat/weechat/issues/2077))
- script: fix default mouse keys ([#2076](https://github.com/weechat/weechat/issues/2076))
- scripts: fix crash on script unload when a hook is created in a buffer close callback ([#2067](https://github.com/weechat/weechat/issues/2067))
- tcl: fix truncation of long integer returned by function hdata_long
- trigger: fix memory leak when adding a new trigger with `/trigger` command

## Version 4.2.3 (2024-05-31)

### Fixed

- xfer: fix send of data on the DCC chat buffer after `/upgrade` if the buffer was opened before the upgrade ([#2092](https://github.com/weechat/weechat/issues/2092))
- irc: fix crash in split of IRC message containing a newline if the server is not given
- core, relay: fix include directory of libzstd

## Version 4.2.2 (2024-04-07)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### Bug fixes

- core: fix reset to initial scroll position after search of text in buffer ([#2093](https://github.com/weechat/weechat/issues/2093))
- core: add missing mouse events "alt-ctrl-button2" and "alt-ctrl-button3"
- exec: remove trailing space on buffers with free content when line numbers are not displayed
- exec: add missing exec tags in lines of buffers with free content ([#2086](https://github.com/weechat/weechat/issues/2086))
- irc: add missing tags on self action messages when capability echo-message is enabled ([#2074](https://github.com/weechat/weechat/issues/2074))
- python: fix truncation of unsigned long long integer returned by function string_parse_size
- relay: set the last IRC client disconnection time only after a successful connection ([#2103](https://github.com/weechat/weechat/issues/2103))
- script: always display list of scripts when searching scripts with `/script search` ([#2077](https://github.com/weechat/weechat/issues/2077))
- script: fix default mouse keys ([#2076](https://github.com/weechat/weechat/issues/2076))
- scripts: fix crash on script unload when a hook is created in a buffer close callback ([#2067](https://github.com/weechat/weechat/issues/2067))
- tcl: fix truncation of long integer returned by function hdata_long
- trigger: fix memory leak when adding a new trigger with `/trigger` command

### Tests

- core: fix tests on function strftimeval on Alpine

## Version 4.2.1 (2024-01-22)

### Bug fixes

- irc: fix random date displayed when a received message contains tags but no "time" ([#2064](https://github.com/weechat/weechat/issues/2064))

## Version 4.2.0 (2024-01-21)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add variable "opening" in buffer, do not send buffer signals when the buffer is opening
- core: store microseconds in buffer lines ([#649](https://github.com/weechat/weechat/issues/649))
- core: evaluate expressions even when the suffix is missing (`}` by default) ([#2042](https://github.com/weechat/weechat/issues/2042), [#1714](https://github.com/weechat/weechat/issues/1714))
- core: add syntax highlighting in evaluation of expressions with `raw_hl:string` and `hl:string`, add option weechat.color.eval_syntax_colors ([#2042](https://github.com/weechat/weechat/issues/2042))
- core: add option `search_history` in command `/input`, add key `Ctrl`+`r` to search in commands history, add key context "histsearch" ([#2040](https://github.com/weechat/weechat/issues/2040))
- core: add option weechat.look.buffer_search_history ([#2040](https://github.com/weechat/weechat/issues/2040))
- core: add key `Ctrl`+`o` to send command found and insert next one in input ([#2040](https://github.com/weechat/weechat/issues/2040))
- core: add buffer variables "text_search_direction", "text_search_history" and "text_search_ptr_history" ([#2040](https://github.com/weechat/weechat/issues/2040))
- core: move key `Ctrl`+`r` to `Ctrl`+`s` ([#2040](https://github.com/weechat/weechat/issues/2040))
- core: move key `Ctrl`+`s`, `Ctrl`+`u` to `Alt`+`Shift`+`U` ([#2040](https://github.com/weechat/weechat/issues/2040))
- core: display only version with command `/version`, add options `-o` and `-ol` in command `/upgrade`
- core: add number of processes in command `/sys waitpid`
- core, alias, trigger: allow wildcard in commands `/bar`, `/filter`, `/item`, `/proxy`, `/alias` and `/trigger` ([#1956](https://github.com/weechat/weechat/issues/1956))
- api: add support of format/translation of command arguments description line by line ([#2005](https://github.com/weechat/weechat/issues/2005))
- api: add function string_concat ([#2005](https://github.com/weechat/weechat/issues/2005))
- api: add functions util_strftimeval, util_parse_time, printf_datetime_tags, printf_y_datetime_tags ([#649](https://github.com/weechat/weechat/issues/649))
- api: add argument "date_usec" in hook_print callback ([#649](https://github.com/weechat/weechat/issues/649))
- api: add property "type" in function buffer_get_string
- api: add info "mouse"
- buflist: jump to previous/next buffer displayed in buflist item with ctrl+wheel up/down on a buflist item ([#1473](https://github.com/weechat/weechat/issues/1473))
- irc: add option irc.look.display_host_wallops
- irc: add server option "anti_flood" (now in milliseconds), remove server options "anti_flood_prio_{high|low}" ([#1039](https://github.com/weechat/weechat/issues/1039))
- irc: add option irc.look.list_buffer
- irc: change default value of server option "tls_priorities" to `NORMAL`
- irc: add support of RGB colors in messages, add option irc.color.term_remap ([#2025](https://github.com/weechat/weechat/issues/2025))
- irc: add tags "nick_xxx" and "host_xxx" in all messages, including self and server messages
- irc: add option irc.look.ignore_tag_messages ([#989](https://github.com/weechat/weechat/issues/989))
- relay: change default value of option relay.network.tls_priorities to `NORMAL`
- trigger: change format of variables `${tg_date}` from "%Y-%m-%d %H:%M:%S" to "%FT%T.%f" ([#649](https://github.com/weechat/weechat/issues/649))
- trigger: rename local variable "trigger_filter" to "filter" on monitor buffer ([#2037](https://github.com/weechat/weechat/issues/2037))

### Bug fixes

- core: fix crash on plugin reload when using musl libc ([#2052](https://github.com/weechat/weechat/issues/2052))
- core: fix infinite loop in display when the chat area is too small ([#2053](https://github.com/weechat/weechat/issues/2053))
- core: fix value of buffer variable "num_history" when the value defined in option weechat.history.max_commands is reached
- core: remove incorrect warning when binding keys `F10` to `F20` ([#2039](https://github.com/weechat/weechat/issues/2039))
- core: call hook config when options are removed
- core: display an error with command `/history N` when N is not a valid integer
- core: fix memory leak when config version is invalid or not supported
- core: fix crash when "config_version" is present in a configuration file without a value
- core: display an error on startup if environment variable "HOME" is not set
- core: fix crash when a custom bar item name is already used by a default bar item ([#2034](https://github.com/weechat/weechat/issues/2034))
- core: fix random timeouts when a lot of concurrent processes are launched with hook_process ([#2033](https://github.com/weechat/weechat/issues/2033))
- api: return NULL instead of empty infolist "key" when context is not found
- irc: check if arguments are not NULL in some infos
- irc: fix info "irc_is_message_ignored" ([#2059](https://github.com/weechat/weechat/issues/2059))
- irc: fix display of self messages when the message split fails due to inconsistent max lengths sent by the server in message 005
- irc: display messages 730/731 (monitored nicks online/offline) even if command `/notify` was not used ([#2049](https://github.com/weechat/weechat/issues/2049))
- irc: remove trailing "\r\n" in signals "irc_out" and "irc_outtags" when messages are queued
- irc: fix target buffer of IRC message 337 (whois reply: "is hiding their idle time")
- irc: revert compute of nick colors to case-sensitive way, deprecate again infos "irc_nick_color" and "irc_nick_color_name" ([#194](https://github.com/weechat/weechat/issues/194), [#2032](https://github.com/weechat/weechat/issues/2032))
- relay: close properly connection with the IRC client in case of server disconnection ([#2038](https://github.com/weechat/weechat/issues/2038))
- ruby: fix use of NULL variable when displaying exception

### Tests

- core: add tests on plugin config and plugin API info functions
- irc: add tests on info functions

### Build

- core: make libintl.h required if CMake option ENABLE_NLS is enabled ([#2031](https://github.com/weechat/weechat/issues/2031))
- ruby: add detection of Ruby 3.3

## Version 4.1.3 (2024-01-20)

### Bug fixes

- core: fix crash on plugin reload when using musl libc ([#2052](https://github.com/weechat/weechat/issues/2052))
- core: fix infinite loop in display when the chat area is too small ([#2053](https://github.com/weechat/weechat/issues/2053))
- irc: check if arguments are not NULL in some infos
- irc: fix info "irc_is_message_ignored" ([#2059](https://github.com/weechat/weechat/issues/2059))
- irc: fix display of self messages when the message split fails due to inconsistent max lengths sent by the server in message 005

## Version 4.1.2 (2023-12-03)

### Bug fixes

- core: fix value of buffer variable "num_history" when the value defined in option weechat.history.max_commands is reached
- core: remove incorrect warning when binding keys `F10` to `F20` ([#2039](https://github.com/weechat/weechat/issues/2039))
- core: fix memory leak when config version is invalid or not supported
- core: fix crash when "config_version" is present in a configuration file without a value
- core: display an error on startup if environment variable "HOME" is not set
- irc: remove trailing "\r\n" in signals "irc_out" and "irc_outtags" when messages are queued
- irc: fix target buffer of IRC message 337 (whois reply: "is hiding their idle time")
- relay: close properly connection with the IRC client in case of server disconnection ([#2038](https://github.com/weechat/weechat/issues/2038))
- ruby: fix use of NULL variable when displaying exception

## Version 4.1.1 (2023-10-26)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### Bug fixes

- core: fix crash when a custom bar item name is already used by a default bar item ([#2034](https://github.com/weechat/weechat/issues/2034))
- core: fix random timeouts when a lot of concurrent processes are launched with hook_process ([#2033](https://github.com/weechat/weechat/issues/2033))
- irc: revert compute of nick colors to case-sensitive way, deprecate again infos "irc_nick_color" and "irc_nick_color_name" ([#194](https://github.com/weechat/weechat/issues/194), [#2032](https://github.com/weechat/weechat/issues/2032))

### Build

- core: make libintl.h required if CMake option ENABLE_NLS is enabled ([#2031](https://github.com/weechat/weechat/issues/2031))

## Version 4.1.0 (2023-10-15)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add completion "eval_variables", used in completion of `/eval`
- core: add command `/sys` to show resource limits/usage and suspend WeeChat process, add key `Ctrl`+`z` to suspend WeeChat ([#985](https://github.com/weechat/weechat/issues/985))
- core: ignore key bindings with empty command
- core: add support of quotes in commands `/key bind` and `/key bindctxt`
- core: evaluate command given to `/repeat` with contextual variables ([#2007](https://github.com/weechat/weechat/issues/2007))
- core: add option `callbacks` in command `/debug`
- core: add option type "enum" ([#1973](https://github.com/weechat/weechat/issues/1973))
- core: add options weechat.buffer.* to save buffer properties set by user, add option `setauto` in command `/buffer` ([#352](https://github.com/weechat/weechat/issues/352))
- core: add parameters and key bindings to move to edges of current area with commands `/cursor go` and `/cursor move` ([#1282](https://github.com/weechat/weechat/issues/1282))
- core: add variables "_chat_focused_line_bol" and "_chat_focused_line_eol" in focus data ([#1955](https://github.com/weechat/weechat/issues/1955))
- api: add function hook_url, add option `url` in command `/debug` ([#1723](https://github.com/weechat/weechat/issues/1723))
- api: add support of path to variable and hashtable comparison in function hdata_compare ([#1066](https://github.com/weechat/weechat/issues/1066))
- api: add infos "nick_color_ignore_case" and "nick_color_name_ignore_case" ([#194](https://github.com/weechat/weechat/issues/194))
- api: add info "buffer" ([#1962](https://github.com/weechat/weechat/issues/1962))
- buflist: add support of item names in command `/buflist refresh`, add completions "buflist_items" and "buflist_items_used"
- buflist: increase max number of buflist items from 3 to 5 ([#1703](https://github.com/weechat/weechat/issues/1703))
- fset: add variable `allowed_values` in options, add options fset.color.allowed_values and fset.color.allowed_values_selected
- fset: allow long type name in type filter
- irc: add count for all nick modes in output of `/names` ([#97](https://github.com/weechat/weechat/issues/97), [#2020](https://github.com/weechat/weechat/issues/2020))
- irc: add count and mode filter in command `/names` ([#98](https://github.com/weechat/weechat/issues/98))
- irc: compute color in case-insensitive way, reintroduce infos "irc_nick_color" and "irc_nick_color_name", add support of server name ([#194](https://github.com/weechat/weechat/issues/194))
- irc: add buffer for /list reply, add options irc.color.list_buffer_line_selected, irc.color.list_buffer_line_selected_bg, irc.look.list_buffer_sort, irc.look.list_buffer_scroll_horizontal, irc.look.new_list_position, irc.look.list_buffer_topic_strip_colors ([#1972](https://github.com/weechat/weechat/issues/1972))
- irc: display commands 716/717 in private buffer (if present) ([#146](https://github.com/weechat/weechat/issues/146))
- irc: create default options irc.ctcp.* when file irc.conf is created ([#1974](https://github.com/weechat/weechat/issues/1974))
- irc: evaluate options irc.ctcp.* ([#1974](https://github.com/weechat/weechat/issues/1974))
- irc: build dynamically the list of CTCPs supported in reply to "CTCP CLIENTINFO" ([#1974](https://github.com/weechat/weechat/issues/1974))
- irc: remove Git revision and compilation date from CTCP VERSION reply ([#1974](https://github.com/weechat/weechat/issues/1974))
- irc: remove default CTCP replies FINGER and USERINFO ([#1974](https://github.com/weechat/weechat/issues/1974))
- irc, xfer: add support of passive DCC ([#2004](https://github.com/weechat/weechat/issues/2004), [#487](https://github.com/weechat/weechat/issues/487))
- script: rename parameters up/down/go to -up/-down/-go in command `/script`
- script: allow jump to the last script with command `/script -go end`
- script: allow commands `/script autoload`, `/script noautoload`, `/script toggleautoload` with scripts not present in the repository ([#1980](https://github.com/weechat/weechat/issues/1980))
- trigger: add options `-o`, `-ol`, `-i` and `-il` in command `/trigger list` ([#1953](https://github.com/weechat/weechat/issues/1953))

### Bug fixes

- core: fix zombie processes after fork (hook process or connect) ([#1994](https://github.com/weechat/weechat/issues/1994))
- core: fix generation of TOTP on Big Endian systems ([#2021](https://github.com/weechat/weechat/issues/2021))
- core: fix cursor position after `/plugin list -i` or `/plugin list -il`
- core: display focus hashtable for debug even if no key is matching
- fset: add local key bindings during the buffer creation
- fset: remove extra spaces between min and max values when second format is used
- fset: fix mouse actions when second format is used
- fset: apply option fset.color.help_description ([#1988](https://github.com/weechat/weechat/issues/1988))
- irc: move value `-all` at the end of completions for command `/ignore del`
- irc: fix memory leak when joining channels with keys
- irc: fix unexpected message sent to server when part of the second line of an IRC command ([#1992](https://github.com/weechat/weechat/issues/1992))
- irc: fix display of country code in message 344 received as whois geo info ([#1736](https://github.com/weechat/weechat/issues/1736))
- irc: add missing "account-tag" in list of supported capabilities
- irc: add channel in "autojoin" server option only when the channel is actually joined ([#1990](https://github.com/weechat/weechat/issues/1990))
- relay: synchronize nick modes with IRC client upon connection ([#1984](https://github.com/weechat/weechat/issues/1984))
- script: add local key bindings during the buffer creation
- script: add parameters up/down/go in `/help script` and command completion
- script: fix cursor position after `/script list -i` or `/script list -il`
- script: fix buffer used by command `/script list -i|-il|-o|-ol`
- xfer: display an error message when opening file for read or write fails ([#2010](https://github.com/weechat/weechat/issues/2010))

### Tests

- core: add tests on GUI buffer functions

### Build

- core: fix build error if CMake option ENABLE_NLS is turned to off or if required dependencies are not found ([#2026](https://github.com/weechat/weechat/issues/2026))
- core, logger, relay: make zstd dependency optional ([#2024](https://github.com/weechat/weechat/issues/2024))

## Version 4.0.8 (2024-01-20)

### Bug fixes

- core: fix crash on plugin reload when using musl libc ([#2052](https://github.com/weechat/weechat/issues/2052))
- core: fix infinite loop in display when the chat area is too small ([#2053](https://github.com/weechat/weechat/issues/2053))
- irc: check if arguments are not NULL in some infos
- irc: fix info "irc_is_message_ignored" ([#2059](https://github.com/weechat/weechat/issues/2059))
- irc: fix display of self messages when the message split fails due to inconsistent max lengths sent by the server in message 005

## Version 4.0.7 (2023-12-03)

### Bug fixes

- core: fix value of buffer variable "num_history" when the value defined in option weechat.history.max_commands is reached
- core: remove incorrect warning when binding keys `F10` to `F20` ([#2039](https://github.com/weechat/weechat/issues/2039))
- core: fix memory leak when config version is invalid or not supported
- core: fix crash when "config_version" is present in a configuration file without a value
- core: display an error on startup if environment variable "HOME" is not set
- irc: remove trailing "\r\n" in signals "irc_out" and "irc_outtags" when messages are queued
- irc: fix target buffer of IRC message 337 (whois reply: "is hiding their idle time")
- relay: close properly connection with the IRC client in case of server disconnection ([#2038](https://github.com/weechat/weechat/issues/2038))
- ruby: fix use of NULL variable when displaying exception

## Version 4.0.6 (2023-10-26)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### Bug fixes

- core: fix crash when a custom bar item name is already used by a default bar item ([#2034](https://github.com/weechat/weechat/issues/2034))
- core: fix generation of TOTP on Big Endian systems ([#2021](https://github.com/weechat/weechat/issues/2021))
- irc: move value `-all` at the end of completions for command `/ignore del`
- irc: fix memory leak when joining channels with keys

### Build

- core: fix build error if CMake option ENABLE_NLS is turned to off or if required dependencies are not found ([#2026](https://github.com/weechat/weechat/issues/2026), [#2031](https://github.com/weechat/weechat/issues/2031))

## Version 4.0.5 (2023-09-24)

### New features

- core: automatically backup config file read if it has an unsupported version ([#2013](https://github.com/weechat/weechat/issues/2013))
- core: display a message when a configuration file is updated to a newer version
- python: make stub (weechat.pyi) compatible with Python 3.8 and 3.9 ([#2006](https://github.com/weechat/weechat/issues/2006))

### Bug fixes

- irc: add option irc.look.open_pv_buffer_echo_msg to open private buffer on self message when capability echo-message is enabled ([#2016](https://github.com/weechat/weechat/issues/2016))
- irc: fix title of private buffers wrongly set to own address when capability echo-message is enabled ([#2016](https://github.com/weechat/weechat/issues/2016))
- irc: fix autojoin of channels when private buffers are opened ([#2012](https://github.com/weechat/weechat/issues/2012))
- irc: fix string comparison when CASEMAPPING is set to "ascii"
- script: fix removal of script in system directory while trying to install a script ([#2019](https://github.com/weechat/weechat/issues/2019))
- script: fix autoload of multiple scripts at once with `/script autoload` ([#2018](https://github.com/weechat/weechat/issues/2018))
- script: fix crash when a `/script` command triggers another `/script` command ([#923](https://github.com/weechat/weechat/issues/923))
- xfer: fix memory leak on plugin unload

### Tests

- irc: add tests on server functions

## Version 4.0.4 (2023-08-22)

### Bug fixes

- core: fix integer overflow when setting integer option with `++N` or `--N`
- core: fix increment/decrement of options weechat.notify.*
- irc: add missing tags on multiline messages ([#1987](https://github.com/weechat/weechat/issues/1987))
- irc: fix redirection of command `/list` when the reply doesn't start with message 321 (start of /list)
- irc: fix wrong time displayed for CTCP messages received from self nick ([#2000](https://github.com/weechat/weechat/issues/2000))
- logger: remove trailing empty line in display of backlog ([#2002](https://github.com/weechat/weechat/issues/2002))
- perl: fix display of non-ASCII chars after load of a script with Perl >= 5.38 ([#1996](https://github.com/weechat/weechat/issues/1996))
- script: adjust scroll after command `/script go N`
- scripts: fix function string_parse_size on 32-bit systems (python and ruby) ([#1999](https://github.com/weechat/weechat/issues/1999))
- xfer: fix conversion of string to IPv4 on 32-bit systems ([#1999](https://github.com/weechat/weechat/issues/1999))

### Tests

- irc: fix tests on function irc_join_compare_join_channel ([#1997](https://github.com/weechat/weechat/issues/1997))
- scripts: fix tests of functions print_date_tag, print_y_date_tags and hook_timer on 32-bit systems ([#1999](https://github.com/weechat/weechat/issues/1999))

## Version 4.0.3 (2023-08-08)

### Bug fixes

- core: fix input length and crash after delete of line ([#1989](https://github.com/weechat/weechat/issues/1989))
- irc: fix display of self CTCP message containing bold attribute ([#1981](https://github.com/weechat/weechat/issues/1981))
- irc: fix memory leak in IRC message parser
- irc: fix switch to channel manually joined when server option autojoin_dynamic is on and option irc.look.buffer_switch_autojoin is off ([#1982](https://github.com/weechat/weechat/issues/1982))
- irc: fix display of outgoing notice with channel when capability "echo-message" is enabled ([#1991](https://github.com/weechat/weechat/issues/1991))
- relay: fix display of IRC CTCP messages received from client ([#1986](https://github.com/weechat/weechat/issues/1986))

### Build

- doc: display a warning if a locale is missing with fallback to English for auto-generated content ([#1985](https://github.com/weechat/weechat/issues/1985))

## Version 4.0.2 (2023-07-12)

### Bug fixes

- core: fix renaming of options with command `/item rename` ([#1978](https://github.com/weechat/weechat/issues/1978))
- core: don't send "key_pressed" signal again for the same key press ([#1976](https://github.com/weechat/weechat/issues/1976))
- core: don't send "key_combo_*" signals for incomplete keys ([#1976](https://github.com/weechat/weechat/issues/1976))
- core: add key `Ctrl`+`Backspace` in /help key ([#1975](https://github.com/weechat/weechat/issues/1975))
- core: keep keys `ctrl-H` and `ctrl-?` (in lower case) if they were manually bound to custom commands in a previous version

### Tests

- core: fix hdata tests failure on Alpine 3.18
- relay: fix crash in tests on Alpine 3.18

### Build

- php: fix detection of PHP 8.2 on Alpine 3.18

## Version 4.0.1 (2023-06-30)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### Bug fixes

- core: force key "return" to command "/input return" when migrating legacy keys
- core: display actual key name and command with key `Alt`+`k`, remove key `Alt`+`K` (grab raw key) and associated commands `/input grab_raw_key` and `/input grab_raw_key_command`
- core: check for newline characters in string_is_whitespace_char ([#1968](https://github.com/weechat/weechat/issues/1968))
- api: do not convert option name to lower case in API functions config_set_plugin and config_set_desc_plugin
- guile: fix crash on quit with Guile < 3 ([#1965](https://github.com/weechat/weechat/issues/1965))
- irc: reply to a CTCP request sent to self nick ([#1966](https://github.com/weechat/weechat/issues/1966))
- irc: sent "QUIT" message to servers connected with TLS on `/upgrade`

## Version 4.0.0 (2023-06-24)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: use human readable key bindings, separate keys with comma in combos, remove modifier "meta2-", add option `legacy` in command `/key` ([#1238](https://github.com/weechat/weechat/issues/1238), [task #10317](https://savannah.nongnu.org/task/?10317))
- core: make keys normal options, so they are shown and can be updated with `/set` and `/fset` commands ([task #12427](https://savannah.nongnu.org/task/?12427), [task #11783](https://savannah.nongnu.org/task/?11783))
- core: add key `Alt`+`K` (upper case) to grab raw key and its command ([#1238](https://github.com/weechat/weechat/issues/1238))
- core: add option `key` in command `/debug` ([#1238](https://github.com/weechat/weechat/issues/1238))
- core: force ctrl keys to lower case when they are added ([#1875](https://github.com/weechat/weechat/issues/1875))
- core: use 256 colors by default and always allow 256 colors, find nearest color if less colors are available in terminal ([#1920](https://github.com/weechat/weechat/issues/1920))
- core: insert multiple pasted lines in input instead of sending immediately, add keys to move and delete in a single line and whole input, add option weechat.look.input_multiline_lead_linebreak ([#1502](https://github.com/weechat/weechat/issues/1502), [#1503](https://github.com/weechat/weechat/issues/1503), [#1504](https://github.com/weechat/weechat/issues/1504))
- core: render newline characters in chat line messages ([#1908](https://github.com/weechat/weechat/issues/1908))
- core: don't split on newline characters in printf_date_tags when input_multiline is set ([#1909](https://github.com/weechat/weechat/issues/1909))
- core: add key `l` (lower `L`) in cursor mode to quote line, add variable "_chat_focused_line" in function hashtable sent to hook_focus callback ([#1913](https://github.com/weechat/weechat/issues/1913), [#1914](https://github.com/weechat/weechat/issues/1914))
- core: add option `split_return` in command `/input` ([#1916](https://github.com/weechat/weechat/issues/1916))
- core: send all command line parameters not beginning with a dash to all plugins
- core: add command `/reset` to reset options to their default values
- core: add option `rename` in command `/bar`
- core: add relative move of read marker with `/buffer set unread [+/-]N` ([#1895](https://github.com/weechat/weechat/issues/1895))
- core: add access to hashtable properties in evaluation of expressions ([#1888](https://github.com/weechat/weechat/issues/1888))
- core: display similar command names when a command is unknown ([#1877](https://github.com/weechat/weechat/issues/1877))
- core: rename option weechat.color.status_name_ssl to weechat.color.status_name_tls ([#1903](https://github.com/weechat/weechat/issues/1903))
- core: add option weechat.color.status_name_insecure to display buffer name with a specific color when not connected with TLS to the server
- core, plugins: make many identifiers case-sensitive ([#1872](https://github.com/weechat/weechat/issues/1872), [#398](https://github.com/weechat/weechat/issues/398), [bug #32213](https://savannah.nongnu.org/bugs/?32213))
- core: add item "mouse_status" in default status bar, change default color to lightgreen
- core, trigger: add options weechat.color.chat_status_disabled and weechat.color.chat_status_enabled, remove options trigger.color.trigger and trigger.color.trigger_disabled, add enabled/disabled status color in output of `/filter list` ([#1820](https://github.com/weechat/weechat/issues/1820))
- core: add completions "filters_names_disabled" and "filters_names_enabled", used in completion of `/filter disable` and `/filter enable`
- api: add function config_set_version ([#1238](https://github.com/weechat/weechat/issues/1238))
- api: don't split on newline by default in functions `command` and `command_options` when `input_multiline` is set to 0
- api: add optional argument with version in info "version_number"
- api: add info "auto_load_scripts"
- alias: use lower case for default aliases, rename all aliases to lower case on upgrade ([#1872](https://github.com/weechat/weechat/issues/1872))
- alias: add `$&` to replace all arguments with double quotes escaped ([#1140](https://github.com/weechat/weechat/issues/1140), [#1190](https://github.com/weechat/weechat/issues/1190))
- alias: add options `missing` and `rename` in command `/alias`
- fifo: add support of escaped chars in text or commands sent ([#1950](https://github.com/weechat/weechat/issues/1950))
- fset: add options fset.color.color_name and fset.color.color_name_selected ([#1920](https://github.com/weechat/weechat/issues/1920))
- irc: rename "ssl" options to "tls", connect with TLS and port 6697 by default ([#1903](https://github.com/weechat/weechat/issues/1903))
- irc: add support of capabilities "batch" and "draft/multiline" ([#1292](https://github.com/weechat/weechat/issues/1292), [#1923](https://github.com/weechat/weechat/issues/1923))
- irc: add support of capability "echo-message" ([#139](https://github.com/weechat/weechat/issues/139))
- irc: display CTCP ACTION to channel on the channel buffer ([#207](https://github.com/weechat/weechat/issues/207))
- irc: display STATUSMSG actions differently from standard actions on channels ([#1577](https://github.com/weechat/weechat/issues/1577))
- irc: add modifier "irc_cap_sync_req" ([#1767](https://github.com/weechat/weechat/issues/1767))
- irc: add support of "LINELEN" in message 005 (max message length in bytes) ([#1927](https://github.com/weechat/weechat/issues/1927))
- irc: add support of "UTF8ONLY" in message 005 ([#1688](https://github.com/weechat/weechat/issues/1688))
- irc: add command `/action` ([#201](https://github.com/weechat/weechat/issues/201), [#1577](https://github.com/weechat/weechat/issues/1577))
- irc: add command `/rules` ([#1864](https://github.com/weechat/weechat/issues/1864))
- irc: add command `/knock` ([#7](https://github.com/weechat/weechat/issues/7))
- irc: add server option "registered_mode", add fields "authentication_method" and "sasl_mechanism_used" in server ([#1625](https://github.com/weechat/weechat/issues/1625))
- irc: add option `join` in command `/autojoin`
- irc: use key when /joining in open channel buffer ([#1260](https://github.com/weechat/weechat/issues/1260))
- irc: add option `buffer` in command `/autojoin sort` ([#1876](https://github.com/weechat/weechat/issues/1876))
- irc: add `${username}` in server options "nicks" and "username", change their default values to use it
- irc: add infos "irc_server_cap" and "irc_server_cap_value"
- irc: add option irc.look.display_host_notice
- irc: add tag "new_host_xxx" in message displayed for command CHGHOST ([#1808](https://github.com/weechat/weechat/issues/1808))
- logger: add option logger.file.log_conditions ([#1942](https://github.com/weechat/weechat/issues/1942))
- logger: add info "logger_log_file"
- relay: rename "ssl" options and protocol to "tls" ([#1903](https://github.com/weechat/weechat/issues/1903))
- relay: make TLS certificate/key loading error handling more verbose ([#1558](https://github.com/weechat/weechat/issues/1558))
- relay: add modifiers "relay_client_irc_in", "relay_client_irc_out1" and "relay_client_irc_out" in irc protocol
- relay: add support of capability "echo-message" in irc protocol ([#1949](https://github.com/weechat/weechat/issues/1949))
- relay: add handshake option "escape_commands" in weechat protocol
- trigger: add completions "trigger_names_disabled" and "trigger_names_enabled", used in completion of `/trigger disable` and `/trigger enable`

### Bug fixes

- core: fix refresh of bar item "input_search" after buffer switch in root bars ([#1939](https://github.com/weechat/weechat/issues/1939))
- core: fix completion after newline in input ([#1925](https://github.com/weechat/weechat/issues/1925))
- core: fix partial completion when the common prefix found is empty ([#340](https://github.com/weechat/weechat/issues/340))
- core: display a specific error when trying to bind a key without area in mouse context
- core: fix display of key with command `/key bindctxt <context> <key>`
- core: fix default value of bar options ([#846](https://github.com/weechat/weechat/issues/846))
- core: allow any valid boolean value in command `/bar set <name> separator xxx`
- core: run config hooks only when value or default value is actually changed in set/reset/unset functions
- core: fix crash in case of NULL message sent to function gui_chat_printf_y_date_tags ([#1883](https://github.com/weechat/weechat/issues/1883))
- core: allow command `/input move_next_word` going to the end of line ([#1881](https://github.com/weechat/weechat/issues/1881))
- core: ignore incomplete ctrl/meta/meta2 codes in keys
- core: fix display glitch in command errors when a wide char is set in option weechat.look.command_chars ([#1871](https://github.com/weechat/weechat/issues/1871))
- core: fix update of terminal title in some terminals like suckless terminal (stterm) ([#1882](https://github.com/weechat/weechat/issues/1882))
- core: fix infinite loop on startup when running some gui commands before the switch to core buffer is performed ([#1917](https://github.com/weechat/weechat/issues/1917))
- api: readjust string size in function string_dyn_free when string is not freed
- buflist: do not display keys added in default context on first load
- exec: remove trailing "M" (carriage return) in output of commands
- fset: remove scroll to top of fset buffer when options are added or removed ([#1892](https://github.com/weechat/weechat/issues/1892))
- guile: fix crash when plugin is loaded on GNU/Hurd ([#1951](https://github.com/weechat/weechat/issues/1951))
- irc: fix format of IRC tags displayed in messages (use "=" to separate key from value, do not convert "_" to "-") ([#1929](https://github.com/weechat/weechat/issues/1929))
- irc: reset all internal servers variables when disconnecting
- irc: start from the beginning of nicks at automatic reconnection ([#337](https://github.com/weechat/weechat/issues/337), [#965](https://github.com/weechat/weechat/issues/965))
- irc: fix join of channels in "autojoin" server option on first connection to server if auto reconnection is performed ([#1873](https://github.com/weechat/weechat/issues/1873))
- irc: update autojoin option with redirected channels when autojoin_dynamic is enabled ([#1898](https://github.com/weechat/weechat/issues/1898))
- irc: update secure data when server autojoin option contains `${sec.data.xxx}` and option autojoin_dynamic is enabled ([#1934](https://github.com/weechat/weechat/issues/1934))
- irc: don't switch to buffer of joined channel if it was neither manually joined nor present in server autojoin option
- irc: fix target buffer for commands 432/433 (erroneous nickname/nickname already in use) when the nickname looks like a channel
- irc: display command 437 on server buffer when nickname cannot change while banned on channel ([#88](https://github.com/weechat/weechat/issues/88))
- irc: add messages 415 (cannot send message to channel) and 742 (mode cannot be set)
- irc: add missing tag "log3" in notify messages
- irc: add missing tags "irc_cap" and "log3" in cap messages (client capability)
- irc: fix split of CTCP message with no arguments
- irc: remove extra space in CTCP ACTION message sent without arguments
- logger: fix display of multiline messages in backlog ([#1926](https://github.com/weechat/weechat/issues/1926))
- lua: fix crash with print when the value to print is not a string ([#1904](https://github.com/weechat/weechat/issues/1904), [#1905](https://github.com/weechat/weechat/issues/1905))
- relay: fix crash on `/upgrade` when at least a client is connected with weechat protocol
- relay: fix connection with IRC clients sending "CAP REQ :" (without capability) and not sending "CAP END" ([#1040](https://github.com/weechat/weechat/issues/1040))
- ruby: fix crash on quit when a child process is still running ([#1889](https://github.com/weechat/weechat/issues/1889), [#1915](https://github.com/weechat/weechat/issues/1915))
- ruby: fix crash in display of exception backtrace with Ruby 3 ([#1631](https://github.com/weechat/weechat/issues/1631), [#1886](https://github.com/weechat/weechat/issues/1886))
- script: remove trailing "J" (line feed char) in source of scripts displayed
- spell: check buffer pointer received in info "spell_dict"
- trigger: make default triggers "cmd_pass", "cmd_pass_register" and "server_pass" compatible with multiline input ([#1935](https://github.com/weechat/weechat/issues/1935))
- typing: fix crash when pointer buffer is not received in callback for signal "input_text_changed" ([#1869](https://github.com/weechat/weechat/issues/1869))
- typing: remove nicks typing even when option typing.look.enabled_self is off ([#1718](https://github.com/weechat/weechat/issues/1718))

### Tests

- core: add tests on URL functions
- gui: add tests on bar and key functions
- alias: add tests on alias functions
- irc: check tags in messages displayed by IRC plugin
- irc: add tests on function irc_server_alloc_with_url
- irc: add tests on message/notice/action/CTCP sent
- logger: add tests on tail functions
- relay: add tests on "irc" protocol

### Build

- core: remove build with autotools ([#1860](https://github.com/weechat/weechat/issues/1860))
- core: remove RPM packaging
- core: remove build of .bz2 and .zst files in `make dist`
- core: remove obsolete cpack config
- core: add "stable-number" and "devel-number" in script version.sh
- core: add quotes around paths in CMake files ([#29](https://github.com/weechat/weechat/issues/29))
- doc: convert docgen.py to C, remove autogen files from repository, add parameter `--doc-gen` to `weechat-headless` binary, add CMake option "ENABLE_DOC_INCOMPLETE"

## Version 3.8 (2023-01-08)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add option weechat.look.chat_space_right ([#1862](https://github.com/weechat/weechat/issues/1862))
- core: allow value "0" in buffer property "unread" to remove read marker from buffer
- core: add command `/allbuf`
- core: add command `/hotlist`
- core: move some `/input` actions to commands `/allbuf`, `/buffer` and `/hotlist`
- core: improve case convert and insensitive char comparisons ([#258](https://github.com/weechat/weechat/issues/258))
- core: add color attributes "blink" and "dim" (half bright) ([#1855](https://github.com/weechat/weechat/issues/1855))
- core: allow command `/toggle` to create option before setting the value, if allowed in the section ([#1837](https://github.com/weechat/weechat/issues/1837))
- core: add signals "buffer_user_input_xxx" and "buffer_user_closing_xxx" for buffers created with `/buffer add` ([#1848](https://github.com/weechat/weechat/issues/1848))
- core: add identifier in buffer lines ([#901](https://github.com/weechat/weechat/issues/901))
- core: add option `unicode` in command `/debug`
- api: add Curl options for versions 7.64.0 to 7.87.0
- api: add functions string_strcmp and string_strncmp
- api: rename char comparison functions "utf8_char*" to "string_char*"
- api: return arithmetic difference between chars in functions string_charcmp, string_charcasecmp, string_charcasecmp_range, string_strcasecmp, string_strcasecmp_range, string_strncasecmp, string_strncasecmp_range, string_strcmp_ignore_chars
- api: return newly allocated string in functions string_tolower and string_toupper
- api: add function utf8_strncpy
- trigger: add regex command "y" to translate chars, set default regex command to "s" (regex replace) ([#1510](https://github.com/weechat/weechat/issues/1510))

### Bug fixes

- core: fix color when the delimiter is not followed by a background color ([#1867](https://github.com/weechat/weechat/issues/1867))
- core: display chars the same way in chat and bars, replace tabulations by spaces in bars, display chars < 32 with letter in chat, do not display soft hyphens, zero width spaces and all non-printable chars ([#1659](https://github.com/weechat/weechat/issues/1659), [#1669](https://github.com/weechat/weechat/issues/1669), [#1770](https://github.com/weechat/weechat/issues/1770))
- core: fix context info in buffers with free content ([#1832](https://github.com/weechat/weechat/issues/1832))
- core: keep terminal title unchanged when option weechat.look.window_title is set to empty value ([#1835](https://github.com/weechat/weechat/issues/1835), [#1836](https://github.com/weechat/weechat/issues/1836))
- core: fix crash when setting invalid color in option with null value ([#1844](https://github.com/weechat/weechat/issues/1844))
- api: do not check conditions defined in option weechat.look.hotlist_add_conditions when adding buffer in hotlist with function buffer_set
- api: fix function strcmp_ignore_chars with case-sensitive comparison and wide chars starting with the same byte
- api: send NULL values to config section callbacks in scripting API ([#1843](https://github.com/weechat/weechat/issues/1843))
- api: fix function string_cut when there are non printable chars in suffix
- api: do not expect any return value in callbacks "callback_change" and "callback_delete" of function config_new_option (scripting API)
- irc: properly rename private buffer on nick changes or privmsg/notice message when new nick is the same with different case
- irc: do not join channels in server autojoin option after reconnection to the server ([#560](https://github.com/weechat/weechat/issues/560), [bug #21529](https://savannah.nongnu.org/bugs/?21529))
- irc: escape backslashes in raw buffer ([#1838](https://github.com/weechat/weechat/issues/1838))
- trigger: fix variables sent to focus callback ([#1858](https://github.com/weechat/weechat/issues/1858))

### Tests

- ci: remove use of repository ppa:ondrej/php, use standard PHP version (8.1) from Ubuntu 22.04
- core: add script check_scripts.sh
- core: add script check_curl_symbols.py
- gui: add tests on input functions
- scripts: add tests on config functions

### Build

- core: add CMake test called "notests" when tests are not compiled
- core: rename scripts: build-debian.sh to build_debian.sh, build-test.sh to build_test.sh, git-version.sh to set_git_version.sh
- debian: change dependency guile-2.2-dev to guile-3.0-dev
- python: remove support of Python 2.x
- ruby: add detection of Ruby 3.2
- spell: add detection of enchant-2 ([#1859](https://github.com/weechat/weechat/issues/1859))

## Version 3.7.1 (2022-10-21)

### Bug fixes

- trigger: execute trigger command on appropriate buffer for hooks command, command_run, line, modifier and print ([#1841](https://github.com/weechat/weechat/issues/1841))

## Version 3.7 (2022-10-09)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add option `-save` in command `/upgrade` ([#1630](https://github.com/weechat/weechat/issues/1630))
- core: add option weechat.look.highlight_disable_regex and buffer property "highlight_disable_regex" ([#1798](https://github.com/weechat/weechat/issues/1798))
- core: sort filters by name ([#1695](https://github.com/weechat/weechat/issues/1695))
- core: add key `Alt`+`Backspace` to delete previous word, change key `Ctrl`+`w` to delete previous word until whitespace ([#559](https://github.com/weechat/weechat/issues/559))
- api: rename function string_build_with_split_string to string_rebuild_split_string, add arguments "index_start" and "index_end"
- api: add info "uptime_current"
- api: add function crypto_hash_file
- api: add support of priority in function hook_line ([#1821](https://github.com/weechat/weechat/issues/1821))
- api: add function string_parse_size
- api: add function file_compress
- buflist: add variable `${hotlist_priority_number}` (integer version of `${hotlist_priority}`)
- irc: display SETNAME command in channels and private buffers, add options irc.color.message_setname and irc.look.smart_filter_setname ([#1805](https://github.com/weechat/weechat/issues/1805))
- irc: add option irc.look.display_pv_nick_change
- logger: add options to rotate and compress log files: logger.file.rotation_compression_level, logger.file.rotation_compression_type and logger.file.rotation_size_max ([#314](https://github.com/weechat/weechat/issues/314))
- spell: allow special dict value "-" to disable spell checking on a specific buffer ([#1699](https://github.com/weechat/weechat/issues/1699))
- trigger: add elapsed time for trigger execution on monitor buffer when trigger debug is set, add option trigger.color.identifier ([#1806](https://github.com/weechat/weechat/issues/1806))
- trigger: add variable `${tg_hook_type}` ([#1765](https://github.com/weechat/weechat/issues/1765))

### Bug fixes

- core: fix wrong terminal title on terminal resize ([#1702](https://github.com/weechat/weechat/issues/1702))
- core: fix page scroll in bare display ([#1830](https://github.com/weechat/weechat/issues/1830))
- api: change type of argument remaining_calls in hook_timer callback from string to integer (in scripts)
- api: change type of argument object_id in upgrade_new callback from string to integer (in scripts)
- irc: fix duplicated channels in autojoin option when autojoin_dynamic is enabled ([#1795](https://github.com/weechat/weechat/issues/1795))
- irc: fix display of TOPIC and QUIT messages with an empty trailing parameter ([#1797](https://github.com/weechat/weechat/issues/1797))
- irc: fix parsing of messages with trailing spaces and no trailing parameter ([#1803](https://github.com/weechat/weechat/issues/1803))
- irc: add missing tag "irc_numeric" in all numeric IRC commands ([#1804](https://github.com/weechat/weechat/issues/1804))
- irc: display an error message when using command `/dcc` without xfer plugin loaded
- irc: display ACCOUNT and CHGHOST commands in private buffers
- irc: fix extract of isupport value when it is last in list and without value ([#1807](https://github.com/weechat/weechat/issues/1807))
- irc: fix target buffer of generic errors when they contain a target nick ([#1814](https://github.com/weechat/weechat/issues/1814))
- irc: fix display of message 350 (whois, gateway) ([#1815](https://github.com/weechat/weechat/issues/1815))
- irc: replace chars "\01" by spaces in CTCP replies ([#1819](https://github.com/weechat/weechat/issues/1819))
- irc: fix message when disconnecting from server in case of high lag when server option autoreconnect is off ([#1708](https://github.com/weechat/weechat/issues/1708))
- irc: set local variable "filter" when doing `/server raw xxx` with raw buffer already opened ([#1448](https://github.com/weechat/weechat/issues/1448))
- guile: fix function hdata_get_string
- javascript: fix return of long value in functions infolist_time, hdata_long and hdata_time
- php: fix function hdata_compare
- relay: fix parsing of IRC messages received from clients ([#1796](https://github.com/weechat/weechat/issues/1796))
- relay: fix refresh of relay buffer after `/upgrade`
- ruby: fix function hdata_get_string
- scripts: fix issue with year ≥ 2038 in functions infolist_new_var_time, print_date_tags and print_y_date_tags (plugins: python/lua/tcl/guile/javascript)
- scripts: fix issue with long interval in function hook_timer (plugins: python/ruby/lua/tcl/guile/javascript/php)
- trigger: fix error on monitor buffer creation when trigger debug is >= 1 and monitor buffer is closed
- trigger: escape arguments with double quotes in output of `/trigger input|output|recreate` ([#190](https://github.com/weechat/weechat/issues/190))
- xfer: fix crash when closing DCC chat buffer
- xfer: disconnect all active DCC chats and files on `/upgrade`
- xfer: fix refresh of xfer buffer after `/upgrade`
- xfer: fix DCC file receive on Termux ([#1811](https://github.com/weechat/weechat/issues/1811))

### Tests

- ci: switch from Ubuntu 20.04 to 22.04
- ci: remove macOS 10.15, add macOS 12
- core: add tests on filter functions
- scripts: add tests on hdata functions
- scripts: fix run of Guile test script
- xfer: add tests on file functions

## Version 3.6 (2022-07-10)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add command `/item` to create custom bar items ([#808](https://github.com/weechat/weechat/issues/808))
- core: add bar item "spacer" ([#1700](https://github.com/weechat/weechat/issues/1700))
- core: add case conversion in evaluation of expressions with `lower:string` and `upper:string` ([#1778](https://github.com/weechat/weechat/issues/1778))
- core: move detailed list of hooks from command `/plugin listfull` to `/debug hooks <plugin>`
- core: allow to remove multiple filters at once with command `/filter del`
- api: allow to catch multiple signals in functions hook_signal and hook_hsignal ([#1780](https://github.com/weechat/weechat/issues/1780))
- irc: rename option `save` to `apply` in command `/autojoin`
- irc: add support of RPL_HELPSTART, RPL_HELPTXT and RPL_ENDOFHELP (messages 524, 704, 705, 706) ([#1772](https://github.com/weechat/weechat/issues/1772))
- php: add support of PHP 8.2 ([#1787](https://github.com/weechat/weechat/issues/1787))

### Bug fixes

- core: fix bad window size on startup with some terminals like [kitty](https://github.com/kovidgoyal/kitty) ([#1769](https://github.com/weechat/weechat/issues/1769))
- api: run hook_print callback also on empty messages
- buflist: fix memory leak when reading config and changing option buflist.look.sort
- irc: remove channel from autojoin option when manually closing a buffer with `/buffer close` or `/close`
- irc: fix add of channel to autojoin option when joining a channel with a buffer still opened
- relay: fix save of channels in autojoin option when JOIN and PART commands are received from an IRC relay client ([#1771](https://github.com/weechat/weechat/issues/1771))
- trigger: add `${buffer.notify} > 0` in conditions of default trigger "beep"
- trigger: fix completion of command `/trigger add` when there are spaces in the following arguments
- trigger: fix memory leak in command `/trigger addinput`

## Version 3.5 (2022-03-27)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: search in message tags when tags are displayed with `/debug tags`
- core: add support of date and tags in messages displayed in buffers with free content, add function printf_y_date_tags ([#1746](https://github.com/weechat/weechat/issues/1746))
- irc: add command `/autojoin`, add server option "autojoin_dynamic"
- irc: add IRC message tags in messages displayed ([#1680](https://github.com/weechat/weechat/issues/1680))
- relay: add `zstd` ([Zstandard](https://facebook.github.io/zstd/)) compression in weechat protocol, remove option `compression` from `init` command, rename option relay.network.compression_level to relay.network.compression
- trigger: add variables `${tg_tag_irc_xxx}` containing IRC message tags ([#1680](https://github.com/weechat/weechat/issues/1680))

### Bug fixes

- core: fix memory leak when removing a line on a buffer with free content
- core: remove obsolete option weechat.plugin.debug ([#1744](https://github.com/weechat/weechat/issues/1744))
- core: fix search of commands with UTF-8 chars in name when option weechat.look.command_incomplete is on ([#1739](https://github.com/weechat/weechat/issues/1739))
- core: fix display of hotlist in buflist after changing value of option weechat.look.hotlist_sort ([#1733](https://github.com/weechat/weechat/issues/1733))
- api: add function buffer_new_props ([#1759](https://github.com/weechat/weechat/issues/1759))
- api: fix add of infolist items in hashtable when prefix contains UTF-8 chars in function hashtable_add_from_infolist ([#1739](https://github.com/weechat/weechat/issues/1739))
- guile: remove disabling of guile gmp allocator with Guile ≥ 3.0.8
- irc: fix completion of channel topic with UTF-8 chars ([#1739](https://github.com/weechat/weechat/issues/1739))
- irc: fix parsing of messages 311, 312, 327 (whois) and 314 (whowas) in case of missing parameters
- irc: fix parsing of message 223 (m_filter) sent by InspIRCd server ([#1751](https://github.com/weechat/weechat/issues/1751))
- irc: fix parsing of message 338 (whois, host) sent by Rizon server ([#1737](https://github.com/weechat/weechat/issues/1737))
- irc: fix display of message 344 received as whois geo info ([#1736](https://github.com/weechat/weechat/issues/1736))
- irc: fix display of message 901 (you are now logged out) ([#1758](https://github.com/weechat/weechat/issues/1758))
- irc: fix display of IRC numeric messages with no parameters
- python: fix crash in hook callbacks after script loading failure ([#1740](https://github.com/weechat/weechat/issues/1740))
- scripts: allow NULL in parameters "default_value" and "value" of function config_new_option ([#1761](https://github.com/weechat/weechat/issues/1761))
- scripts: auto-load scripts with supported extensions only ([#1698](https://github.com/weechat/weechat/issues/1698))
- tcl: add constant `$::weechat::WEECHAT_NULL` ([#1761](https://github.com/weechat/weechat/issues/1761))
- trigger: fix search of triggers with UTF-8 chars in name ([#1739](https://github.com/weechat/weechat/issues/1739))
- xfer: fix auto-accept of server/nick when the server name contains UTF-8 chars ([#1739](https://github.com/weechat/weechat/issues/1739))

### Tests

- ci: add build of Debian packages
- core: add tests on GUI chat functions

### Build

- debian: change dependency libargon2-0-dev to libargon2-dev ([debian #1005703](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=1005703))
- ruby: add detection of Ruby 3.1

## Version 3.4.1 (2022-03-13)

### Bug fixes

- core: set again TLS verification functions after options weechat.network.gnutls_ca_system and weechat.network.gnutls_ca_user are changed ([#1763](https://github.com/weechat/weechat/issues/1763), [CVE-2022-28352](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2022-28352))

## Version 3.4 (2021-12-18)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add support of static arrays in hdata
- core: add command `/toggle`
- api: add parameters pointers, extra_vars and options in function hdata_search
- api: add user variables in evaluation of expressions with `define:name,value`
- api: add IRC message parameters `param1` to `paramN` and `num_params` in output of irc_message_parse
- irc: allow quotes around IRC message in command `/server fakerecv`
- trigger: hide key and password in command `/msg nickserv setpass nick key password`
- trigger: add support of option `-server` when hiding passwords in command `/msg nickserv register`

### Bug fixes

- core: fix memory leak in evaluated expression `split:number,seps,flags,xxx` when multiple "strip_items" are given
- core: fix random integer number with large range in evaluation of expressions on GNU/Hurd
- core: fix access to integer/long/time arrays in hdata
- api: fix search of option when the section is not given in functions config_search_option and config_search_section_option
- irc: fix join of channels with long name ([#1717](https://github.com/weechat/weechat/issues/1717))
- irc: fix parsing of parameters in all IRC messages ([#1666](https://github.com/weechat/weechat/issues/1666))
- irc: fix parsing of CAP message when there is no prefix ([#1707](https://github.com/weechat/weechat/issues/1707))
- irc: fix parsing of TAGMSG message when there is a colon before the channel

### Documentation

- doc: remove tester's guide
- doc: add dark theme (automatic, following browser/desktop settings)
- doc: make build reproducible
- doc: disable web fonts
- doc: switch from prettify to pygments for syntax highlighting

### Tests

- ci: add build with CMake and Ninja
- ci: add build on macOS 11

### Build

- ruby: add detection of Ruby 3.0 ([#1721](https://github.com/weechat/weechat/issues/1721), [#1605](https://github.com/weechat/weechat/issues/1605))
- core: add targets "changelog" and "rn" to build HTML version of ChangeLog and release notes (CMake build only)

## Version 3.3 (2021-09-19)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: change key `Alt`+`h` to `Alt`+`h`, `Alt`+`c` (clear hotlist)
- core: add options `hotlist_remove_buffer`, `hotlist_restore_buffer` and `hotlist_restore_all` in command `/input`, add default keys `Alt`+`h`, `Alt`+`m` (remove buffer), `Alt`+`h`, `Alt`+`r` (restore hotlist in current buffer) and `Alt`+`h`, `Alt`+`Shift`+`R` (restore hotlist in all buffers)
- core: add option `certs` in command `/debug`
- core: add options `-o`, `-ol`, `-i` and `-il` in command `/plugin list`
- api: add split of string and shell arguments in evaluation of expressions with `split:number,seps,flags,xxx` and `split_shell:number,xxx`
- api: add `${re:repl_index}` to get the index of replacement in function string_eval_expression ([#1689](https://github.com/weechat/weechat/issues/1689))
- api: add random integer number in evaluation of expressions with `random:min,max`
- api: add function string_cut
- api: add function file_copy ([#1667](https://github.com/weechat/weechat/issues/1667))
- api: remember insertion order in hashtables
- api: add keys/values with tags in output of irc_message_parse_to_hashtable ([#1654](https://github.com/weechat/weechat/issues/1654))
- irc: add option `-parted` in command `/allchan` ([#1685](https://github.com/weechat/weechat/issues/1685))
- irc: allow signals "irc_raw_in" and "irc_in" to eat messages ([#1657](https://github.com/weechat/weechat/issues/1657))
- irc: implement IRCv3.2 SASL authentication, add command `/auth`, reconnect by default to the server in case of SASL authentication failure ([#413](https://github.com/weechat/weechat/issues/413))
- irc: add support of capability "message-tags" and TAGMSG messages ([#1654](https://github.com/weechat/weechat/issues/1654))
- irc: enable all capabilities by default (if supported by server and WeeChat), change default value of option irc.server_default.capabilities to `*` ([#320](https://github.com/weechat/weechat/issues/320))
- irc: add options irc.look.display_account_message and irc.look.display_extended_join ([#320](https://github.com/weechat/weechat/issues/320))
- irc: add command `/setname`, add support of message and capability "setname" ([#1653](https://github.com/weechat/weechat/issues/1653))
- irc: always set realname in nicks even when extended-join capability is not enabled ([#1653](https://github.com/weechat/weechat/issues/1653))
- irc: add support of FAIL/WARN/NOTE messages ([#1653](https://github.com/weechat/weechat/issues/1653))
- irc: drop support of DH-BLOWFISH and DH-AES SASL mechanisms ([#175](https://github.com/weechat/weechat/issues/175))
- typing: new plugin "typing": display users currently writing messages on IRC channel/private buffers

### Bug fixes

- core: fix decoding of attributes in basic ANSI colors ([#1678](https://github.com/weechat/weechat/issues/1678))
- api: fix function string_match with joker in the string if multiple words matched in input string
- irc: fix send of empty JOIN when connecting to a server with only parted channels ([#1638](https://github.com/weechat/weechat/issues/1638))
- irc: fix SASL authentication when AUTHENTICATE message is received with a server name ([#1679](https://github.com/weechat/weechat/issues/1679))
- irc: remove unneeded message about Diffie-Hellman shared secret exchange during SSL connection to server ([#857](https://github.com/weechat/weechat/issues/857))
- irc: escape/unescape IRC message tags values ([#1654](https://github.com/weechat/weechat/issues/1654))
- irc: set notify level to "private" for received WALLOPS
- script: fix move of installed script on another filesystem ([#1667](https://github.com/weechat/weechat/issues/1667))

### Documentation

- add Spanish FAQ ([#1656](https://github.com/weechat/weechat/issues/1656))
- add Serbian translations ([#1655](https://github.com/weechat/weechat/issues/1655))

### Tests

- ci: switch to PHP 8.0
- ci: add build on macOS

### Build

- core: fix build on macOS ([#1662](https://github.com/weechat/weechat/issues/1662))
- lua: add detection of Lua 5.4
- php: add support of PHP 8.0 and 8.1 ([#1599](https://github.com/weechat/weechat/issues/1599), [#1668](https://github.com/weechat/weechat/issues/1668))

## Version 3.2.1 (2021-09-04)

### Bug fixes

- relay: fix crash when decoding a malformed websocket frame ([CVE-2021-40516](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-40516))

## Version 3.2 (2021-06-13)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: use XDG directories by default (config, data, cache, runtime) ([#1285](https://github.com/weechat/weechat/issues/1285))
- core: add option weechat.network.gnutls_ca_system, rename option weechat.network.gnutls_ca_file to weechat.network.gnutls_ca_user (now evaluated), delete and reload certificates when options are changed ([#972](https://github.com/weechat/weechat/issues/972))
- core: evaluate option weechat.plugin.path, change default value to `${weechat_data_dir}/plugins`
- core: add options to customize commands executed on system signals received (SIGHUP, SIGQUIT, SIGTERM, SIGUSR1, SIGUSR2) ([#1595](https://github.com/weechat/weechat/issues/1595))
- core: quit WeeChat by default when signal SIGHUP is received in normal run, reload configuration in weechat-headless ([#1595](https://github.com/weechat/weechat/issues/1595))
- core: add signals "cursor_start" and "cursor_end"
- api: add function crypto_hmac ([#1628](https://github.com/weechat/weechat/issues/1628))
- api: add translated string in evaluation of expressions with `translate:xxx`
- api: add evaluation of WeeChat directories with `${weechat_xxx_dir}` in evaluated strings
- api: add optional key "directory" in hashtable options of function/modifier string_eval_path_home
- api: add supported prefixes `${weechat_xxx_dir}` in function mkdir_home
- api: add infos "weechat_config_dir", "weechat_data_dir", "weechat_cache_dir" and "weechat_runtime_dir"
- api: add support of pointer names in function string_eval_expression (direct and in hdata)
- api: add info "weechat_daemon"
- buflist: add option buflist.format.tls_version
- fifo: change default value of option fifo.file.path to `${weechat_runtime_dir}/weechat_fifo_${info:pid}`
- irc: add support of SASL mechanisms SCRAM-SHA-1, SCRAM-SHA-256 and SCRAM-SHA-512 ([#1628](https://github.com/weechat/weechat/issues/1628))
- irc: add variable `${target}` (target nick) in commands `/kick` and `/kickban`
- irc: add bar item "tls_version", add options irc.color.item_tls_version_ok, irc.color.item_tls_version_deprecated and irc.color.item_tls_version_insecure ([#1622](https://github.com/weechat/weechat/issues/1622))
- irc: evaluate server options "sasl_key" and "ssl_cert"
- logger: change default value of option logger.file.path to `${weechat_data_dir}/logs`
- python: add stub for WeeChat API ([#1377](https://github.com/weechat/weechat/issues/1377))
- relay: evaluate option relay.network.ssl_cert_key, change default value to `${weechat_config_dir}/ssl/relay.pem`
- script: change default value of option script.scripts.path to `${weechat_cache_dir}/script`
- trigger: add variables `${tg_shell_argc}` and `${tg_shell_argvN}` in command trigger evaluated strings ([#1624](https://github.com/weechat/weechat/issues/1624))
- xfer: change default value of option xfer.file.download_path to `${weechat_data_dir}/xfer`

### Bug fixes

- core: split startup commands before evaluating them ([#1643](https://github.com/weechat/weechat/issues/1643))
- core: set server name when connecting to server with TLS (SNI extension) only if it's not an IPV4/IPv6 ([#1635](https://github.com/weechat/weechat/issues/1635))
- core: use function mallinfo2 instead of mallinfo when available ([#1636](https://github.com/weechat/weechat/issues/1636))
- core: display a warning when the file with certificate authorities is not found (option weechat.network.gnutls_ca_file)
- core: evaluate left/right part of comparison after split on the comparison operator in `${if:xxx}` ([#1627](https://github.com/weechat/weechat/issues/1627))
- core: prevent switching to start of visited buffers when jumping to next ([#1591](https://github.com/weechat/weechat/issues/1591), [#1592](https://github.com/weechat/weechat/issues/1592))
- core: recreate buflist and fset bars on `/reload` when WeeChat is started without configuration files ([#1618](https://github.com/weechat/weechat/issues/1618))
- buflist: fix comparison of hotlists in option buflist.look.sort ([#1621](https://github.com/weechat/weechat/issues/1621))
- irc: split server command before evaluating it ([#1643](https://github.com/weechat/weechat/issues/1643))
- xfer: make file transfer fail when option xfer.file.auto_rename is off and file already exists ([#1633](https://github.com/weechat/weechat/issues/1633))

### Tests

- ci: switch from Ubuntu 18.04 to 20.04
- trigger: add tests on main trigger functions

### Build

- core: remove build option CA_FILE
- core: set WeeChat home to empty string by default in CMake and autotools

## Version 3.1 (2021-03-07)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add options weechat.look.hotlist_update_on_buffer_switch and weechat.look.read_marker_update_on_buffer_switch ([#992](https://github.com/weechat/weechat/issues/992), [#993](https://github.com/weechat/weechat/issues/993))
- core: add option sec.crypt.passphrase_command to read passphrase from an external program on startup, remove option sec.crypt.passphrase_file ([#141](https://github.com/weechat/weechat/issues/141))
- core: improve debug in command `/eval`: display more verbose debug with two `-d`, add indentation and colors
- core: add options `setvar` and `delvar` in command `/buffer`, rename option `localvar` to `listvar`
- core: add buffer local variable "completion_default_template" (evaluated) to override the value of option "weechat.completion.default_template" ([#1600](https://github.com/weechat/weechat/issues/1600))
- core: add option `recreate` in command `/filter`
- core: add raw string in evaluation of expressions with `raw:xxx` ([#1611](https://github.com/weechat/weechat/issues/1611))
- core: add evaluation of conditions in evaluation of expressions with `eval_cond:xxx` ([#1582](https://github.com/weechat/weechat/issues/1582))
- api: add info_hashtable "secured_data"
- irc: add info "irc_is_message_ignored"
- irc: add server option "default_chantypes", used when the server does not send them in message 005 ([#1610](https://github.com/weechat/weechat/issues/1610))
- trigger: add variable `${tg_trigger_name}` in command trigger evaluated strings ([#1580](https://github.com/weechat/weechat/issues/1580))

### Bug fixes

- core: fix quoted line in cursor mode ([#1602](https://github.com/weechat/weechat/issues/1602))
- core: fix wrong size of the new window after vertical split ([#1612](https://github.com/weechat/weechat/issues/1612))
- core: do not remove quotes in arguments of command `/eval` as they can be part of the evaluated expression/condition ([#1601](https://github.com/weechat/weechat/issues/1601))
- core: display an error when the buffer is not found with command `/command -buffer`
- buflist: add option buflist.look.use_items to speed up display of buflist ([#1613](https://github.com/weechat/weechat/issues/1613))
- irc: add bar item "irc_nick_prefix"
- irc: fix separator between nick and host in bar item "irc_nick_host"
- irc: fix completion of commands `/halfop` and `/dehalfop`

### Documentation

- do not build weechat-headless man page if headless binary is disabled ([#1607](https://github.com/weechat/weechat/issues/1607))

## Version 3.0.1 (2021-01-31)

### Bug fixes

- exec: fix search of command by identifier
- spell: fix refresh of bar item "spell_suggest" when the input becomes empty ([#1586](https://github.com/weechat/weechat/issues/1586))
- spell: fix crash with IRC color codes in command line ([#1589](https://github.com/weechat/weechat/issues/1589))

## Version 3.0 (2020-11-11)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- api: add optional list of colors in infos "nick_color" and "nick_color_name" ([#1565](https://github.com/weechat/weechat/issues/1565))
- api: add argument "bytes" in function string_dyn_concat
- api: add function string_color_code_size ([#1547](https://github.com/weechat/weechat/issues/1547))
- exec: add option `-oerr` to send stderr to buffer (now disabled by default) ([#1566](https://github.com/weechat/weechat/issues/1566))
- fset: add option fset.look.auto_refresh ([#1553](https://github.com/weechat/weechat/issues/1553))
- irc: add pointer to irc_nick in focus of bar item "buffer_nicklist" ([#1535](https://github.com/weechat/weechat/issues/1535), [#1538](https://github.com/weechat/weechat/issues/1538))
- irc: allow to send text on buffers with commands `/allchan`, `/allpv` and `/allserv`
- irc: evaluate command executed by commands `/allchan`, `/allpv` and `/allserv` ([#1536](https://github.com/weechat/weechat/issues/1536))
- script: add option script.scripts.download_enabled ([#1548](https://github.com/weechat/weechat/issues/1548))
- trigger: add variable "tg_argc" in data set by command trigger ([#1576](https://github.com/weechat/weechat/issues/1576))
- trigger: add variable "tg_trigger_name" in data set by all triggers ([#1567](https://github.com/weechat/weechat/issues/1567), [#1568](https://github.com/weechat/weechat/issues/1568))

### Bug fixes

- core: set "notify_level" to 3 if there is a highlight in the line ([#1529](https://github.com/weechat/weechat/issues/1529))
- core: do not add line with highlight and tag "notify_none" to hotlist ([#1529](https://github.com/weechat/weechat/issues/1529))
- irc: remove SASL timeout message displayed by error after successful SASL authentication ([#1515](https://github.com/weechat/weechat/issues/1515))
- irc: send all channels in a single JOIN command when reconnecting to the server ([#1551](https://github.com/weechat/weechat/issues/1551))
- script: do not automatically download list of scripts on startup if the file is too old ([#1548](https://github.com/weechat/weechat/issues/1548))
- spell: properly skip WeeChat and IRC color codes when checking words in input ([#1547](https://github.com/weechat/weechat/issues/1547))
- trigger: fix recursive calls to triggers using regex ([#1546](https://github.com/weechat/weechat/issues/1546))
- trigger: add `${tg_tags} !!- ,notify_none,` in conditions of default trigger "beep" ([#1529](https://github.com/weechat/weechat/issues/1529))

### Tests

- core: add tests on GUI line functions

### Build

- core: disable debug by default in autotools build
- tests: fix compilation with CppUTest ≥ 4.0

## Version 2.9 (2020-07-18)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add bar option "color_bg_inactive": color for window bars in inactive window ([#732](https://github.com/weechat/weechat/issues/732))
- core: add Alacritty title escape sequence support ([#1517](https://github.com/weechat/weechat/issues/1517))
- core: display notify level for current buffer with command `/buffer notify` ([#1505](https://github.com/weechat/weechat/issues/1505))
- core: count only visible nicks in bar item "buffer_nicklist_count", add bar items "buffer_nicklist_count_groups" and "buffer_nicklist_count_all" ([#1506](https://github.com/weechat/weechat/issues/1506))
- core: set default size for input bar to 0 (automatic) ([#1498](https://github.com/weechat/weechat/issues/1498))
- core: add default key `Alt`+`Enter` to insert a newline ([#1498](https://github.com/weechat/weechat/issues/1498))
- core: add flag "input_multiline" in buffer ([#984](https://github.com/weechat/weechat/issues/984), [#1063](https://github.com/weechat/weechat/issues/1063))
- core: add a scalable WeeChat logo (SVG) ([#1454](https://github.com/weechat/weechat/issues/1454), [#1456](https://github.com/weechat/weechat/issues/1456))
- core: add base 16/32/64 encoding/decoding in evaluation of expressions with `base_encode:base,xxx` and `base_decode:base,xxx`
- core: add case-sensitive wildcard matching comparison operator (`+==*+` and `+!!*+`) and case-sensitive/insensitive include comparison operators (`+==-+`, `+!!-+`, `+=-+`, `+!-+`) in evaluation of expressions
- core: add default key `Alt`+`Shift`+`N` to toggle nicklist bar
- core: add command line option `--stdout` in weechat-headless binary to log to stdout rather than ~/.weechat/weechat.log ([#1475](https://github.com/weechat/weechat/issues/1475), [#1477](https://github.com/weechat/weechat/issues/1477))
- core: reload configuration files on SIGHUP ([#1476](https://github.com/weechat/weechat/issues/1476))
- api: add pointer "_bar_window" in hashtable sent to hook focus callback ([#1450](https://github.com/weechat/weechat/issues/1450))
- api: add info_hashtable "focus_info" ([#1245](https://github.com/weechat/weechat/issues/1245), [#1257](https://github.com/weechat/weechat/issues/1257))
- api: rename function hook_completion_get_string to completion_get_string and hook_completion_list_add to completion_list_add
- api: add functions completion_new, completion_search and completion_free
- api: add hdata "completion_word"
- buflist: add default key `Alt`+`Shift`+`B` to toggle buflist
- buflist: add options enable/disable/toggle in command `/buflist`
- buflist: evaluate option buflist.look.sort so that sort can be customized for each of the three buflist bar items ([#1465](https://github.com/weechat/weechat/issues/1465))
- irc: add support of UTF8MAPPING ([#1528](https://github.com/weechat/weechat/issues/1528))
- irc: display account messages in buffers ([#1250](https://github.com/weechat/weechat/issues/1250))
- python: add WeeChat sharedir python directory to PYTHONPATH ([#1537](https://github.com/weechat/weechat/issues/1537))
- relay: increase default limits for IRC backlog options
- relay: add command "handshake" in weechat relay protocol and nonce to prevent replay attacks, add options relay.network.password_hash_algo, relay.network.password_hash_iterations, relay.network.nonce_size ([#1474](https://github.com/weechat/weechat/issues/1474))
- relay: add command "completion" in weechat relay protocol to perform a completion on a string at a given position ([#1484](https://github.com/weechat/weechat/issues/1484))
- relay: add option relay.network.auth_timeout
- relay: update default colors for client status
- relay: add status "waiting_auth" in irc and weechat protocols ([#1358](https://github.com/weechat/weechat/issues/1358))
- trigger: evaluate arguments of command when the trigger is created ([#1472](https://github.com/weechat/weechat/issues/1472))

### Bug fixes

- core: fix command `/window scroll_beyond_end` when buffer has fewer lines than chat height ([#1509](https://github.com/weechat/weechat/issues/1509))
- core: force buffer property "time_for_each_line" to 0 for buffers with free content ([#1485](https://github.com/weechat/weechat/issues/1485))
- core: don't collapse consecutive newlines in lines displayed before the first buffer is created
- core: don't remove consecutive newlines when pasting text ([#1500](https://github.com/weechat/weechat/issues/1500))
- core: don't collapse consecutive newlines in bar content ([#1500](https://github.com/weechat/weechat/issues/1500))
- core: fix WEECHAT_SHAREDIR with CMake build ([#1461](https://github.com/weechat/weechat/issues/1461))
- core: fix memory leak in calculation of expression on FreeBSD ([#1469](https://github.com/weechat/weechat/issues/1469))
- core: fix resize of a bar when its size is 0 (automatic) ([#1470](https://github.com/weechat/weechat/issues/1470))
- api: fix use of pointer after free in function key_unbind
- api: replace plugin and buffer name by buffer pointer in argument "modifier_data" sent to weechat_print modifier callback ([#42](https://github.com/weechat/weechat/issues/42))
- buflist: add "window" pointer in bar item evaluation only if it's not NULL (if bar type is "window")
- exec: fix use of same task id for different tasks ([#1491](https://github.com/weechat/weechat/issues/1491))
- fifo: fix errors when writing in the FIFO pipe ([#713](https://github.com/weechat/weechat/issues/713))
- guile: enable again `/guile` eval ([#1514](https://github.com/weechat/weechat/issues/1514))
- irc: use new default chantypes "#&" when the server does not send it
- irc: add support of optional server in info "irc_is_nick", fix check of nick using UTF8MAPPING isupport value ([#1528](https://github.com/weechat/weechat/issues/1528))
- irc: fix add of ignore with flags in regex, display full ignore mask in list of ignores ([#1518](https://github.com/weechat/weechat/issues/1518))
- irc: do not remove spaces at the end of users messages received ([#1513](https://github.com/weechat/weechat/issues/1513))
- irc: fix realname delimiter color in WHO/WHOX response ([#1497](https://github.com/weechat/weechat/issues/1497))
- irc: reuse a buffer with wrong type "channel" when a private message is received ([#869](https://github.com/weechat/weechat/issues/869))
- python: fix crash when invalid UTF-8 string is in a WeeChat hashtable converted to a Python dict ([#1463](https://github.com/weechat/weechat/issues/1463))
- relay: add missing field "notify_level" in message "_buffer_line_added" ([#1529](https://github.com/weechat/weechat/issues/1529))
- relay: fix slow send of data to clients when SSL is enabled
- trigger: only return trigger's return code when condition evaluates to true ([#592](https://github.com/weechat/weechat/issues/592))
- trigger: fix truncated trigger command with commands `/trigger` input|output|recreate
- trigger: do not hide values of options with `/set` command in cmd_pass trigger

### Documentation

- add includes directory
- merge 53 auto-generated files into 11 files
- fix broken literal blocks in Japanese docs with Firefox ([#1466](https://github.com/weechat/weechat/issues/1466))

### Tests

- ci: add CI with GitHub Actions, move codecov.io upload to GitHub Actions
- ci: switch to Ubuntu Bionic on Travis CI, use pylint3 to lint Python scripts
- core: run tests on plugins only if the plugins are enabled and compiled
- irc: add tests on IRC color and channel functions

### Build

- javascript: disable build by default and remove Debian packaging of JavaScript plugin ([#360](https://github.com/weechat/weechat/issues/360))
- core: make GnuTLS a required dependency
- core: fix build with CMake 3.17.0
- core: fix build with cygport on Cygwin

## Version 2.8 (2020-03-29)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add variable "old_full_name" in buffer, set during buffer renaming ([#1428](https://github.com/weechat/weechat/issues/1428))
- core: add debug option `-d` in command `/eval` ([#1434](https://github.com/weechat/weechat/issues/1434))
- api: add functions crypto_hash and crypto_hash_pbkdf2
- api: add info "auto_connect" ([#1453](https://github.com/weechat/weechat/issues/1453))
- api: add info "weechat_headless" ([#1433](https://github.com/weechat/weechat/issues/1433))
- buflist: add pointer "window" in bar item evaluation
- irc: add support of fake servers (no I/O, for testing purposes)
- relay: accept hash of password in init command of weechat protocol with option "password_hash" (PBKDF2, SHA256, SHA512)
- relay: reject client with weechat protocol if password or TOTP is received in init command but not set in WeeChat ([#1435](https://github.com/weechat/weechat/issues/1435))

### Bug fixes

- core: fix memory leak in completion
- core: flush stdout/stderr before forking in hook_process function ([#1441](https://github.com/weechat/weechat/issues/1441))
- core: fix evaluation of condition with nested "if" ([#1434](https://github.com/weechat/weechat/issues/1434))
- irc: split AUTHENTICATE message in 400-byte chunks ([#1459](https://github.com/weechat/weechat/issues/1459))
- irc: copy temporary server flag in command `/server copy`
- irc: add nick changes in the hotlist (except self nick change)
- irc: case-insensitive comparison on incoming CTCP command, force upper case on CTCP replies ([#1439](https://github.com/weechat/weechat/issues/1439))
- irc: fix memory leak when the channel topic is changed
- logger: fix crash when logging is disabled on a buffer and the log file was deleted in the meanwhile, when option logger.file.info_lines is on ([#1444](https://github.com/weechat/weechat/issues/1444))
- php: fix crash when loading script with PHP 7.4 ([#1452](https://github.com/weechat/weechat/issues/1452))
- relay: update buffers synchronization when buffers are renamed ([#1428](https://github.com/weechat/weechat/issues/1428))
- script: fix memory leak in read of script repository file if it has invalid content
- script: fix unexpected display of scripts list in buffer with command `/script list -i`
- xfer: send signal "xfer_ended" after the received file has been renamed ([#1438](https://github.com/weechat/weechat/issues/1438))

### Tests

- scripts: fix generation of test scripts with Python 3.8
- core: add tests on function secure_derive_key
- core: add tests on functions util_get_time_diff and util_file_get_content
- irc: add tests on IRC protocol functions and callbacks

### Build

- core: fix Cygwin build
- guile: add detection of Guile 3.0.0 ([#1442](https://github.com/weechat/weechat/issues/1442))
- irc: fix build with GnuTLS < 3.1.0 ([#1431](https://github.com/weechat/weechat/issues/1431))
- php: add detection of PHP 7.4
- ruby: add detection of Ruby 2.7 ([#1455](https://github.com/weechat/weechat/issues/1455))

## Version 2.7.1 (2020-02-20)

### Bug fixes

- irc: fix crash when a new message 005 is received with longer nick prefixes ([CVE-2020-9760](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-9760))
- irc: fix crash when receiving a malformed message 352 (who) ([CVE-2020-9759](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-9759))
- irc: fix crash when receiving a malformed message 324 (channel mode) ([CVE-2020-8955](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-8955))

## Version 2.7 (2019-12-08)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add option weechat.look.nick_color_hash_salt to shuffle nick colors ([#635](https://github.com/weechat/weechat/issues/635))
- core: add different icons sizes (16x16 to 512x512) ([#1347](https://github.com/weechat/weechat/issues/1347))
- core: add file weechat.desktop
- core: add reverse of string for screen in evaluation of expressions with `revscr:xxx`
- core: add length of string (number of chars and on screen) in evaluation of expressions with `length:xxx` and `lengthscr:xxx`
- core: add calculation of expression in evaluation of expressions with `calc:xxx` ([#997](https://github.com/weechat/weechat/issues/997))
- core: add optional default path (evaluated) in completion "filename"
- core: add support of modifiers in evaluation of expressions with `modifier:name,data,string`
- api: add modifier "color_encode_ansi" ([#528](https://github.com/weechat/weechat/issues/528))
- api: add modifier "eval_path_home"
- irc: add filters on raw buffer ([#1000](https://github.com/weechat/weechat/issues/1000))
- irc: add option irc.look.display_pv_warning_address to display a warning in private buffer if the remote nick address has changed ([#892](https://github.com/weechat/weechat/issues/892))
- irc: add server option "ssl_password" ([#115](https://github.com/weechat/weechat/issues/115), [#1416](https://github.com/weechat/weechat/issues/1416))
- irc: add "user" in output of irc_message_parse ([#136](https://github.com/weechat/weechat/issues/136))
- irc: add options irc.color.message_kick and irc.color.reason_kick ([#683](https://github.com/weechat/weechat/issues/683), [#684](https://github.com/weechat/weechat/issues/684))
- logger: add option logger.file.color_lines ([#528](https://github.com/weechat/weechat/issues/528), [#621](https://github.com/weechat/weechat/issues/621))
- script: add options `-ol` and `-il` in command `/script list` to send translated string with list of scripts loaded, display "No scripts loaded" if no scripts are loaded
- xfer: add option xfer.file.download_temporary_suffix with default value ".part" ([#1237](https://github.com/weechat/weechat/issues/1237))

### Bug fixes

- core: set buffer name, short name and title only if the value has changed
- core: fix scrolling up in bare mode when switched to bare mode at the top of the buffer ([#899](https://github.com/weechat/weechat/issues/899), [#978](https://github.com/weechat/weechat/issues/978))
- core: optimize load of configuration files
- core: fix window separators not respecting window splits ([#630](https://github.com/weechat/weechat/issues/630))
- core: fix cursor mode info when prefix_align is none and with words split across lines ([#610](https://github.com/weechat/weechat/issues/610), [#617](https://github.com/weechat/weechat/issues/617), [#619](https://github.com/weechat/weechat/issues/619))
- core: add support of reverse video in ANSI color codes
- core: fixed segfault during excessive evaluation in function string_repeat ([#1400](https://github.com/weechat/weechat/issues/1400))
- buflist: fix extra spaces between buffers when conditions are used to hide buffers (regression introduced in version 2.6) ([#1403](https://github.com/weechat/weechat/issues/1403))
- irc: do not automatically open a channel with name "0" ([#1429](https://github.com/weechat/weechat/issues/1429))
- irc: remove option irc.network.channel_encode, add server option "charset_message" to control which part of the IRC message is decoded/encoded to the target charset ([#832](https://github.com/weechat/weechat/issues/832))
- irc: use path from option xfer.file.upload_path to complete filename in command `/dcc send` ([#60](https://github.com/weechat/weechat/issues/60))
- logger: fix write in log file if it has been deleted or renamed ([#123](https://github.com/weechat/weechat/issues/123))
- python: send "bytes" instead of "str" to callbacks in Python 3 when the string is not UTF-8 valid ([#1389](https://github.com/weechat/weechat/issues/1389))
- relay: send message "_buffer_title_changed" to clients only when the title is changed
- xfer: fix memory leak when a xfer is freed and when the plugin is unloaded

### Tests

- core: add tests on GUI color functions

### Build

- core: fix build on Haiku ([#1420](https://github.com/weechat/weechat/issues/1420))
- core: fix build on Alpine
- core: remove file FindTCL.cmake
- core: display an error on missing dependency in CMake ([#916](https://github.com/weechat/weechat/issues/916), [#956](https://github.com/weechat/weechat/issues/956))
- debian: disable JavaScript plugin on Debian Sid and Ubuntu Eoan
- debian: build with Guile 2.2
- guile: add support of Guile 2.2, disable `/guile eval` ([#1098](https://github.com/weechat/weechat/issues/1098))
- python: add detection of Python 3.8

## Version 2.6 (2019-09-08)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add support of 32767 color pairs ([#1343](https://github.com/weechat/weechat/issues/1343), [#1345](https://github.com/weechat/weechat/issues/1345))
- core: add option `close` in command `/window` ([#853](https://github.com/weechat/weechat/issues/853))
- api: add infos "term_colors" and "term_color_pairs"
- api: add function list_user_data ([#666](https://github.com/weechat/weechat/issues/666))
- api: add argument "strip_items" in function string_split
- buflist: add infolist "buflist" with list of buffer pointers ([#1375](https://github.com/weechat/weechat/issues/1375))
- exec: evaluate option exec.command.shell, change default value to `${env:SHELL}` ([#1356](https://github.com/weechat/weechat/issues/1356))
- fset: add filters `h=xxx` and `he=xxx` to filter options by description (translated or in English)
- irc: make command char optional in server option "command" ([#615](https://github.com/weechat/weechat/issues/615))
- irc: add variables "user_max_length" and "host_max_length" in server structure ([#1387](https://github.com/weechat/weechat/issues/1387))

### Bug fixes

- core: use fixed-width integer for computing nick and hashtable DJB2 key hashes, add values "djb2_32" and "sum_32" for option weechat.look.nick_color_hash ([#1394](https://github.com/weechat/weechat/issues/1394))
- core: create or update option weechat.notify.xxx when function buffer_set is called with "notify" property ([#1390](https://github.com/weechat/weechat/issues/1390))
- core: fix memory leak in case of error when building content of bar item for display ([#1384](https://github.com/weechat/weechat/issues/1384))
- core: send command line parameter to plugins only if the name starts with the plugin name followed by a colon
- core: auto disable upgrade process (command line option `--upgrade`) if the file weechat.upgrade is not found
- core: replace newlines by spaces in argument "completion" of function hook_command ([#538](https://github.com/weechat/weechat/issues/538))
- core: replace char "," by "~" in color codes to separate foreground from background ([#1264](https://github.com/weechat/weechat/issues/1264))
- alias: remove default aliases `/AME` and `/AMSG` ([#1355](https://github.com/weechat/weechat/issues/1355))
- buflist: use extra variables in option buflist.look.display_conditions ([#1393](https://github.com/weechat/weechat/issues/1393))
- irc: fix parsing of messages 346 (invite list), 348 (exception list), 367 (ban list) and 728 (quiet list) when there is a colon before the timestamp ([#1396](https://github.com/weechat/weechat/issues/1396))
- irc: fix memory leak when removing a server
- irc: fix length of user/nick/host in split of messages ([#1387](https://github.com/weechat/weechat/issues/1387))
- irc: quote NICK command argument sent to the server only if there's a ":" in the nick ([#1376](https://github.com/weechat/weechat/issues/1376), [#1319](https://github.com/weechat/weechat/issues/1319))
- irc: return all arguments in the PONG response to a PING ([#1369](https://github.com/weechat/weechat/issues/1369))
- irc: disable server reconnection when the server buffer is closed ([#236](https://github.com/weechat/weechat/issues/236))
- irc: strip spaces at beginning/end of addresses in server option "addresses" ([#195](https://github.com/weechat/weechat/issues/195))
- irc: fix display of enabled/disabled client capabilities received in command CAP ACK ([#151](https://github.com/weechat/weechat/issues/151))
- ruby: fix conversion of big integers on 32bit architecture ([#1395](https://github.com/weechat/weechat/issues/1395))

### Tests

- irc: add tests on IRC ignore, message and nick functions

### Build

- core: fix compilation with autotools on FreeBSD 12.0
- debian: disable JavaScript plugin on Debian Buster/Bullseye ([#1374](https://github.com/weechat/weechat/issues/1374))
- python: compile with Python 3 by default
- python: use pkg-config to detect Python ([#1382](https://github.com/weechat/weechat/issues/1382))

## Version 2.5 (2019-06-06)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: use getopt to parse command line arguments
- core: add option weechat.look.prefix_same_nick_middle ([#930](https://github.com/weechat/weechat/issues/930), [#931](https://github.com/weechat/weechat/issues/931))
- core: add option weechat.look.buffer_time_same ([#1127](https://github.com/weechat/weechat/issues/1127))
- core: use seconds by default in `/repeat` interval, allow unit for the interval
- core: allow text in addition to a command in command `/repeat`
- core: add option `addreplace` in command `/filter` ([#1055](https://github.com/weechat/weechat/issues/1055), [#1312](https://github.com/weechat/weechat/issues/1312))
- api: return allocated string in hook_info callback and function info_get
- api: replace argument "keep_eol" by "flags" in function string_split ([#1322](https://github.com/weechat/weechat/issues/1322))
- api: add function command_options ([#928](https://github.com/weechat/weechat/issues/928))
- api: add function string_match_list
- irc: add bar items "irc_nick", "irc_host" and "irc_nick_host"
- irc: add variable "host" in server structure
- relay: add support of UNIX socket ([#733](https://github.com/weechat/weechat/issues/733), [#1333](https://github.com/weechat/weechat/issues/1333))
- relay: add option relay.weechat.commands ([#928](https://github.com/weechat/weechat/issues/928))
- script: use SHA-512 instead of MD5 for script checksum
- spell: rename aspell plugin to spell ([#1299](https://github.com/weechat/weechat/issues/1299))
- trigger: add hooks "info" and "info_hashtable"
- xfer: rename option xfer.network.speed_limit to xfer.network.speed_limit_send, add option xfer.network.speed_limit_recv ([#269](https://github.com/weechat/weechat/issues/269))

### Bug fixes

- core: don't execute command scheduled by `/repeat` and `/wait` if the buffer does not exist anymore
- core: set max length to 4096 for `/secure passphrase` ([#1323](https://github.com/weechat/weechat/issues/1323))
- core: refilter only affected buffers on filter change ([#1309](https://github.com/weechat/weechat/issues/1309), [#1311](https://github.com/weechat/weechat/issues/1311))
- fset: fix slow refresh of fset buffer during `/reload` ([#1313](https://github.com/weechat/weechat/issues/1313))
- irc: fix parsing of MODE command when there are colons after the first mode argument ([#1296](https://github.com/weechat/weechat/issues/1296))
- irc: fix memory leak in infos "irc_server_isupport" and "irc_server_isupport_value"
- irc: fix length of string for SHA-512, SHA-256 and SHA-1 in help on ssl_fingerprint option
- irc: display an error with `/allchan -current` or `/allpv -current` if the current buffer is not an irc buffer ([#1325](https://github.com/weechat/weechat/issues/1325))
- irc: fix update of channels modes with arguments when joining a channel ([#1324](https://github.com/weechat/weechat/issues/1324))
- irc: quote NICK command argument sent to the server ([#1319](https://github.com/weechat/weechat/issues/1319))
- php: fix memory leak in functions string_eval_expression, string_eval_path_home, key_bind, hook_process_hashtable, hook_hsignal_send, info_get_hashtable, hdata_update
- relay: fix crash when a weechat relay client reloads the relay plugin with `/plugin reload relay` ([#1327](https://github.com/weechat/weechat/issues/1327))
- spell: fix detection of nick followed by the nick completer ([#1306](https://github.com/weechat/weechat/issues/1306), [#1307](https://github.com/weechat/weechat/issues/1307))
- trigger: fix split of hook arguments ([#1322](https://github.com/weechat/weechat/issues/1322))

### Tests

- core: add tests on function util_signal_search

### Build

- core: fix value of libdir in file weechat.pc ([#1341](https://github.com/weechat/weechat/issues/1341), [#1342](https://github.com/weechat/weechat/issues/1342))
- core: fix generation of man page weechat-headless with autotools
- core: add CMake option "ENABLE_CODE_COVERAGE" to compile with code coverage options (CMake ≥ 3.0 is now required)
- core: fix compilation on macOS ([#1308](https://github.com/weechat/weechat/issues/1308))
- lua: add detection of Lua 5.3 with autotools
- ruby: add detection of Ruby 2.6 ([#1346](https://github.com/weechat/weechat/issues/1346))
- tests: fix compilation of tests on FreeBSD

## Version 2.4 (2019-02-17)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: do not automatically add a space when completing "nick:" at the beginning of command line (the space can be added in option weechat.completion.nick_completer)
- core: add default keys `Ctrl`+`F11` / `Ctrl`+`F12` to scroll up/down one page in nicklist (same action as `F11` / `F12`)
- core: add command line option `-t` (or `--temp-dir`) to create a temporary WeeChat home (deleted on exit)
- api: add functions string_base_encode and string_base_decode, remove functions string_encode_base64 and string_decode_base64
- api: add support of Time-based One-Time Password (TOTP), add infos "totp_generate" and "totp_validate"
- buflist: add default keys `Ctrl`+`F1` / `Ctrl`+`F2` to scroll up/down one page in buflist (same action as `F1` / `F2`)
- buflist: add variable `${number2}`, always set with the indented buffer number
- exec: add option exec.command.shell to customize the shell used with `/exec -sh`
- relay: add support of close frame in websocket connection ([#1281](https://github.com/weechat/weechat/issues/1281))
- relay: add support of Time-based One-Time Password (TOTP) as second authentication factor in weechat protocol

### Bug fixes

- core: fix compilation of empty regular expression (not allowed on FreeBSD)
- core: fix forced highlight on messages sent to other buffers ([#1277](https://github.com/weechat/weechat/issues/1277))
- aspell: look for suggestions only if the misspelled word has changed ([#1175](https://github.com/weechat/weechat/issues/1175))
- buflist: add alternate key codes for `F1` / `F2` and `Alt`+`F1` / `Alt`+`F2` (compatibility with terminals)
- buflist: fix warning displayed when script buffers.pl is loaded ([#1274](https://github.com/weechat/weechat/issues/1274))
- irc: fix parsing of whois messages in notify
- irc: fix parsing of MODE, 341 (invite) and CHGHOST commands when there are colons ([#1296](https://github.com/weechat/weechat/issues/1296))
- irc: return IRC color code instead of WeeChat color code when decoding a too short ANSI color sequence
- irc: fix encoding of italic attribute when colors are removed
- irc: fix parsing of "time" message tag on FreeBSD ([#1289](https://github.com/weechat/weechat/issues/1289))
- relay: fix crash on `/upgrade` when the real IP is not set ([#1294](https://github.com/weechat/weechat/issues/1294))
- relay: fix memory leak in connection of client

### Tests

- core: fix UTF-8 and evaluation tests on FreeBSD
- irc: add tests on IRC configuration and protocol functions

### Build

- core: add C compiler flag "-fsigned--char" to force "char" data type to be always signed ([#1277](https://github.com/weechat/weechat/issues/1277))

## Version 2.3 (2018-10-21)

### New features

- core: add repeat of string in evaluation of expressions with `repeat:count,string` ([#958](https://github.com/weechat/weechat/issues/958))
- core: allow specifying buffer number/name for `/buffer localvar` ([#1259](https://github.com/weechat/weechat/issues/1259))
- core: allow multiple arguments in command `/buffer close`
- core: allow multiple options `-r` (or `--run-command`) in command line arguments ([#1248](https://github.com/weechat/weechat/issues/1248))
- core: add command line option `-P` (or `--plugins`) to customize the plugins to load at startup
- core: allow partial buffer name in command `/buffer close` ([#1226](https://github.com/weechat/weechat/issues/1226))
- api: add function hook_line ([#66](https://github.com/weechat/weechat/issues/66))
- irc: display a warning when the value of option irc.server.xxx.autojoin is set to an invalid value
- relay: add real IP in client description ([#1256](https://github.com/weechat/weechat/issues/1256))
- trigger: allow creation of temporary variables with the regex
- trigger: add hook "line"

### Bug fixes

- core: fix evaluation of nested ternary operators ([#1263](https://github.com/weechat/weechat/issues/1263))
- core: fix evaluation of condition when the left operand is an empty string
- core: fix string evaluation with regex replacement when the string is empty
- core: fix check of tags in lines (command `/filter` and hook_print)
- core: fix clear of completion item in case of partial completion ([#1162](https://github.com/weechat/weechat/issues/1162))
- core: send signal "key_pressed" for mouse code only if the string is UTF-8 valid ([#1220](https://github.com/weechat/weechat/issues/1220))
- api: fix memory leak in function string_split
- lua: fix return code of mkdir functions in case of error ([#1267](https://github.com/weechat/weechat/issues/1267))
- scripts: fix duplicated lines in output of script eval (python, perl, ruby, lua and guile)

### Tests

- core: add tests on line and hook functions

### Build

- php: add detection of PHP 7.3

## Version 2.2 (2018-07-14)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: change default value of option weechat.look.hotlist_add_conditions to check connected relay clients via weechat protocol ([#1206](https://github.com/weechat/weechat/issues/1206))
- core: add reverse of string in evaluation of expressions with `rev:xxx` ([#1200](https://github.com/weechat/weechat/issues/1200))
- core: send buffer pointer (when possible) in signal "hotlist_changed" ([#1133](https://github.com/weechat/weechat/issues/1133))
- core: add support of list options in curl ([#826](https://github.com/weechat/weechat/issues/826), [#219](https://github.com/weechat/weechat/issues/219))
- core: allow merge of buffers by name in command `/buffer` ([#1108](https://github.com/weechat/weechat/issues/1108), [#1159](https://github.com/weechat/weechat/issues/1159))
- api: add function hashtable_add_from_infolist
- api: add function string_format_size in scripting API
- irc: add nick, host and log tags in message displayed in private buffer when the nick comes back on the server ([#1221](https://github.com/weechat/weechat/issues/1221))
- irc: add support for IRCv3.2 chghost, add options irc.look.smart_filter_chghost and irc.color.message_chghost ([#640](https://github.com/weechat/weechat/issues/640))
- irc: add support for IRCv3.2 invite-notify ([#639](https://github.com/weechat/weechat/issues/639))
- irc: add support for IRCv3.2 Client Capability Negotiation ([#586](https://github.com/weechat/weechat/issues/586), [#623](https://github.com/weechat/weechat/issues/623))
- irc: display current nick on connected servers in output of `/server list|listfull` ([#1193](https://github.com/weechat/weechat/issues/1193))
- irc: add option `-server` in command `/list` ([#1165](https://github.com/weechat/weechat/issues/1165))
- irc: add indexed ban list, add completion for `/unban` and `/unquiet` ([#597](https://github.com/weechat/weechat/issues/597), [task #11374](https://savannah.nongnu.org/task/?11374), [task #10876](https://savannah.nongnu.org/task/?10876))
- relay: add filtering on protocol in info "relay_client_count"
- trigger: hide password in command `/msg nickserv set password`
- xfer: add option xfer.network.send_ack ([#1171](https://github.com/weechat/weechat/issues/1171))

### Bug fixes

- core: fix TLS handshake failure on server connection when there are multiple addresses in the server ([#1196](https://github.com/weechat/weechat/issues/1196))
- core: count number of chars instead of bytes for suffix in function string_cut
- core: fix delete of previous/next word (keys `Ctrl`+`w` and `Alt`+`d`) ([#1195](https://github.com/weechat/weechat/issues/1195))
- core: fix infinite loop in evaluation of strings ([#1183](https://github.com/weechat/weechat/issues/1183))
- core: change default value of option weechat.look.window_title from "WeeChat ${info:version}" to empty string ([#1182](https://github.com/weechat/weechat/issues/1182))
- buflist: fix crash when setting the option buflist.look.signals_refresh with a list of signals
- fset: fix memory leak when switching the format with `Ctrl`+`x`
- fset: fix truncation of option values when the length is greater than 4096 ([#1218](https://github.com/weechat/weechat/issues/1218))
- fset: fix crash when applying filters after closing the fset buffer ([#1204](https://github.com/weechat/weechat/issues/1204))
- irc: display message 354 (WHOX) received with missing parameters ([#1212](https://github.com/weechat/weechat/issues/1212))
- irc: always set nick away status on WHO response (sent manually or automatically with server option "away_check")
- irc: fix a crash when calling the function hdata_string on the "prefix" variable in the nick
- irc: fix split of messages when server option "split_msg_max_length" is set to 0 (no split) ([#1173](https://github.com/weechat/weechat/issues/1173))
- irc: send whole IRC message including IRCv3 tags in the signals irc_in, irc_in2, irc_raw_in and irc_raw_in2 ([#787](https://github.com/weechat/weechat/issues/787))
- irc: fix memory leak when receiving a message with IRCv3 tags
- guile: fix memory leak in 7 functions returning allocated strings
- lua: fix macros used to return values
- php: fix return code of functions config_write_option and config_write_line
- php: fix memory leak in 72 functions returning allocated strings
- python: fix crash when loading a script with Python ≥ 3.7 ([#1219](https://github.com/weechat/weechat/issues/1219))
- relay: fix socket creation for relay server on OpenBSD ([#1213](https://github.com/weechat/weechat/issues/1213))
- ruby: fix memory leak in 7 functions returning allocated strings
- script: fix memory leak in case of invalid XML content in list of scripts
- scripts: fix memory leak in hook_info callback
- scripts: fix return value of hook_infolist callback (pointer instead of string)
- scripts: return long integer instead of string in function infolist_time
- xfer: set option TCP_NODELAY on socket when receiving a file via DCC ([#1171](https://github.com/weechat/weechat/issues/1171))

### Documentation

- core: split man pages weechat and weechat-headless

### Tests

- core, scripts: add tests on infolists

### Build

- core: fix build with CMake and Ninja
- debian: add package weechat-headless with the headless binary and its man page
- javascript: fix compilation of javascript plugin with autotools on some Linux distributions ([#1208](https://github.com/weechat/weechat/issues/1208))
- python: add detection of Python 3.7

## Version 2.1 (2018-03-18)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add binary weechat-headless to run WeeChat without interface, with optional daemon mode (command line option `--daemon`) ([#1120](https://github.com/weechat/weechat/issues/1120))
- core: add options `-newbuffer`, `-free` and `-switch` in command `/print` ([#1113](https://github.com/weechat/weechat/issues/1113))
- core: add option `-y` in command `/print`, add support of buffers with free content
- core: add option `add` in command `/buffer` ([#1113](https://github.com/weechat/weechat/issues/1113))
- core: add option weechat.completion.partial_completion_templates to force partial completion on specific templates
- api: add hashtable with variables in plugin structure
- api: add time in info "date" (WeeChat compilation date/time) ([#1138](https://github.com/weechat/weechat/issues/1138))
- irc: add server option "split_msg_max_length"
- irc: allow `${irc_server.xxx}` and `${server}` in server evaluated options ([#1144](https://github.com/weechat/weechat/issues/1144))
- logger: add option logger.file.fsync ([#1145](https://github.com/weechat/weechat/issues/1145))
- logger: add option logger.look.backlog_conditions ([#1132](https://github.com/weechat/weechat/issues/1132))
- script: change default value of option script.look.sort from "p,n" to "i,p,n"
- scripts: add configuration file for each script plugin (python.conf, perl.conf, etc.)
- scripts: add `eval` option in script commands and info "xxx_eval" (python, perl, ruby, lua and guile) ([#128](https://github.com/weechat/weechat/issues/128))
- scripts: add infos "xxx_interpreter" and "xxx_version" in script plugins ([#1075](https://github.com/weechat/weechat/issues/1075))
- scripts: add option `version` in script commands ([#1075](https://github.com/weechat/weechat/issues/1075))
- scripts: display the script name in stdout/stderr output from scripts

### Bug fixes

- core: fix regression on execution of hook_print callbacks (introduced in version 2.0)

### Build

- ruby: add detection of Ruby 2.5 ([#1122](https://github.com/weechat/weechat/issues/1122))

## Version 2.0.1 (2017-12-20)

### Bug fixes

- python: fix arguments status/gnutls_rc/sock in hook_connect callback
- python: fix argument fd in hook_fd callback

## Version 2.0 (2017-12-03)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add flag "input_get_empty" in buffer
- core: add signals "buffer_filters_enabled" and "buffer_filters_disabled"
- core: support loading of plugins from path in environment variable "WEECHAT_EXTRA_LIBDIR" ([#971](https://github.com/weechat/weechat/issues/971), [#979](https://github.com/weechat/weechat/issues/979))
- core: make value optional in command `/buffer set` ([#746](https://github.com/weechat/weechat/issues/746), [#1088](https://github.com/weechat/weechat/issues/1088))
- core: allow floating point and hexadecimal numbers in comparison of evaluated values
- core: add option weechat.look.save_config_with_fsync ([#1083](https://github.com/weechat/weechat/issues/1083))
- api: add support of prefix "quiet:" in function key_unbind to quietly remove keys
- api: add argument "recurse_subdirs" in function exec_on_files
- alias: add infolist "alias_default" (list of default aliases)
- buflist: add two new bar items ("buflist2" and "buflist3") using the same format configuration options ([#990](https://github.com/weechat/weechat/issues/990))
- buflist: add option buflist.look.add_newline ([#1027](https://github.com/weechat/weechat/issues/1027))
- fset: new plugin "fset" (fast set of WeeChat and plugins options) ([#584](https://github.com/weechat/weechat/issues/584))
- php: new plugin "php" ([#909](https://github.com/weechat/weechat/issues/909))
- script: add local variable "filter" in the script buffer ([#1037](https://github.com/weechat/weechat/issues/1037))

### Bug fixes

- core: do not change the chat prefix size when a filtered line is added ([#1092](https://github.com/weechat/weechat/issues/1092))
- core: fix display of nicks in nicklist when they are in a group with sub-groups ([#1079](https://github.com/weechat/weechat/issues/1079))
- core, plugins: check return code of strftime function
- core: fix cast of time_t (to "long long" instead of "long") ([#1051](https://github.com/weechat/weechat/issues/1051))
- core: call the config hook when options are renamed or removed
- api: change type of arguments status/gnutls_rc/sock in hook_connect callback from string to integer (in scripts)
- api: change type of argument fd in hook_fd callback from string to integer (in scripts)
- buflist: remove recursive evaluation of extra variables ([#1060](https://github.com/weechat/weechat/issues/1060))
- guile: return integer (0/1) instead of boolean in API functions
- guile: fix return value of static strings in API functions
- irc: do not clear nicklist when joining an already joined channel if the option irc.look.buffer_open_before_join is on ([#1081](https://github.com/weechat/weechat/issues/1081))
- irc: fix CTCP PING reply when the option irc.ctcp.ping is set to non-empty value
- lua: fix boolean return value (as integer) in API functions
- relay: fix parsing of CAP command without arguments in irc protocol, send ACK only if all capabilities received are OK and NAK otherwise ([#1040](https://github.com/weechat/weechat/issues/1040))

### Tests

- core: display an error if the required locale en_US.UTF-8 is not installed
- scripts: add scripting API tests ([#104](https://github.com/weechat/weechat/issues/104))

### Build

- core: fix build with ncurses and separate tinfo ([bug #41245](https://savannah.nongnu.org/bugs/?41245), [#1090](https://github.com/weechat/weechat/issues/1090))
- javascript: fix detection of libv8 with autotools on Ubuntu Trusty

## Version 1.9.1 (2017-09-23)

### Bug fixes

- buflist: fix crash in auto-scroll of bar when the buflist item is not the first item in the bar
- logger: call strftime before replacing buffer local variables ([CVE-2017-14727](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-14727))
- relay: fix send of "PART" command in backlog (irc protocol)

## Version 1.9 (2017-06-25)

### New features

- core: improve speed of nicklist bar item callback
- core: allow index for hdata arrays in evaluation of expressions
- api: allow update of variables "scroll_x" and "scroll_y" in bar_window with function hdata_update
- api: add functions config_option_get_string and hdata_compare
- buflist: add option buflist.look.auto_scroll ([#332](https://github.com/weechat/weechat/issues/332))
- buflist: add keys `F1` / `F2`, `Alt`+`F1` / `Alt`+`F2` to scroll the buflist bar
- buflist: display a warning when the script "buffers.pl" is loaded
- buflist: add support of char "~" in option buflist.look.sort for case-insensitive comparison
- buflist: add variable `${format_name}` in bar item evaluation and option buflist.format.name ([#1020](https://github.com/weechat/weechat/issues/1020))
- buflist: add variables `${current_buffer}` and `${merged}` (booleans "0" / "1") in bar item evaluation
- relay: add option `start` in command `/relay`
- trigger: add "irc_server" and "irc_channel" pointers in data for IRC signal/modifier hooks

### Bug fixes

- core: fix bind of keys with space key, like `Alt`+`Space` ([#603](https://github.com/weechat/weechat/issues/603), [bug #32133](https://savannah.nongnu.org/bugs/?32133))
- core: fix infinite loop when the terminal is closed on the secure password prompt ([#1010](https://github.com/weechat/weechat/issues/1010))
- buflist: fix long mouse gestures
- buflist: fix slow switch of buffer when there are a lot of buffers opened ([#998](https://github.com/weechat/weechat/issues/998))
- buflist: add option `bar` in command `/buflist`, do not automatically add the "buflist" bar when the option buflist.look.enabled is off ([#994](https://github.com/weechat/weechat/issues/994))
- buflist: fix crash on drag & drop of buffers
- irc: don't reset nick properties (prefixes/away/account/realname) on `/names` when the nick already exists ([#1019](https://github.com/weechat/weechat/issues/1019))
- irc: fix memory leak in case of error in "ecdsa-nist256p-challenge" SASL mechanism
- relay: rebind on address after option relay.network.bind_address is changed
- relay: fix parsing of CAP command arguments in irc protocol ([#995](https://github.com/weechat/weechat/issues/995))

## Version 1.8 (2017-05-13)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add option weechat.completion.nick_case_sensitive ([#981](https://github.com/weechat/weechat/issues/981))
- core: add wildcard matching operator (`+=*+` and `+!*+`) in evaluation of expressions ([#611](https://github.com/weechat/weechat/issues/611))
- core: add cut of string in evaluation of expressions with `cut:xxx` (number of chars) and `cutscr:xxx` (number of chars displayed on screen)
- core: add ternary operator (condition) in evaluation of expressions (`${if:condition?value_if_true:value_if_false}`)
- core: add resize of window parents with `/window resize [h/v]size` ([task #11461](https://savannah.nongnu.org/task/?11461), [#893](https://github.com/weechat/weechat/issues/893))
- core: add hotlist pointer in buffer structure
- core: add last start date in output of command `/version` after at least one `/upgrade` ([#903](https://github.com/weechat/weechat/issues/903))
- api: add arraylist functions: arraylist_new, arraylist_size, arraylist_get, arraylist_search, arraylist_insert, arraylist_add, arraylist_remove, arraylist_clear, arraylist_free
- api: add dynamic string functions: string_dyn_alloc, string_dyn_copy, string_dyn_concat, string_dyn_free
- api: add special key "__quiet" in hashtable for function key_bind
- api: add `${re:#}` to get the index of last group captured in function string_eval_expression
- aspell: add options to control delimiters in suggestions: aspell.color.suggestion_delimiter_{dict|word} and aspell.look.suggestion_delimiter_{dict|word} ([#940](https://github.com/weechat/weechat/issues/940))
- buflist: new plugin "buflist" (bar item with list of buffers)
- irc: add option `open` in command `/server` ([#966](https://github.com/weechat/weechat/issues/966))
- irc: send signal "irc_server_lag_changed" and store the lag in the server buffer (local variable)
- irc: send multiple masks by message in commands `/ban`, `/unban`, `/quiet` and `/unquiet`, use ban mask default for nicks in `/quiet` and `/unquiet`, display an error if `/quiet` and `/unquiet` are not supported by server ([#579](https://github.com/weechat/weechat/issues/579), [#15](https://github.com/weechat/weechat/issues/15), [#577](https://github.com/weechat/weechat/issues/577))
- irc: add option `-include` in commands `/allchan`, `/allpv` and `/allserv` ([#572](https://github.com/weechat/weechat/issues/572))
- irc: don't smart filter modes given to you ([#530](https://github.com/weechat/weechat/issues/530), [#897](https://github.com/weechat/weechat/issues/897))
- script: remove option script.scripts.url_force_https, use HTTPS by default in option script.scripts.url

### Bug fixes

- core: fix memory leak in display of mouse event debug info
- core: fix command `/cursor stop` (do not toggle cursor mode) ([#964](https://github.com/weechat/weechat/issues/964))
- core: fix delayed refresh when the signal SIGWINCH is received (terminal resized), send signal "signal_sigwinch" after refreshes ([#902](https://github.com/weechat/weechat/issues/902))
- irc: fix update of server addresses on reconnection when the evaluated content has changed ([#925](https://github.com/weechat/weechat/issues/925))
- irc: fix crash in case of invalid server reply during SASL authentication with DH-BLOWFISH or DH-AES mechanism
- irc: fix double decoding of IRC colors in messages sent/displayed by commands `/msg` and `/query` ([#943](https://github.com/weechat/weechat/issues/943))
- irc: fix parsing of message 324 (modes) when there is a colon before the modes ([#913](https://github.com/weechat/weechat/issues/913))
- relay: check buffer pointer received in "sync" and "desync" commands (weechat protocol) ([#936](https://github.com/weechat/weechat/issues/936))
- relay: remove buffer from synchronized buffers when it is closed (fix memory leak)

### Build

- core: fix compilation on FreeBSD with autotools ([#276](https://github.com/weechat/weechat/issues/276))
- python: add detection of Python 3.6
- ruby: add detection of Ruby 2.4 ([#895](https://github.com/weechat/weechat/issues/895))

## Version 1.7.1 (2017-04-22)

### Bug fixes

- irc: fix parsing of DCC filename ([CVE-2017-8073](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-8073))

## Version 1.7 (2017-01-15)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add option weechat.look.align_multiline_words ([#411](https://github.com/weechat/weechat/issues/411), [#802](https://github.com/weechat/weechat/issues/802))
- core: add optional command prefix in completion templates "commands", "plugins_commands" and "weechat_commands"
- core: add optional arguments in completion template, sent to the callback
- core: add option `time` in command `/debug`
- core, xfer: display more information on fork errors ([#573](https://github.com/weechat/weechat/issues/573))
- core: add a slash before commands completed in arguments of `/command`, `/debug time`, `/key bind`, `/key bindctxt`, `/mute`, `/repeat`, `/wait`
- core: add a warning in header of configuration files to not edit by hand ([#851](https://github.com/weechat/weechat/issues/851))
- api: add info "uptime" (WeeChat uptime)
- api: add info "pid" (WeeChat PID) ([#850](https://github.com/weechat/weechat/issues/850))
- alias: add a slash before commands completed in arguments of `/alias`
- exec: add option `-oc` in command `/exec` to execute commands in process output, don't execute commands by default with `-o` ([#877](https://github.com/weechat/weechat/issues/877))
- fifo: add file fifo.conf and option fifo.file.path to customize FIFO pipe path/filename ([#850](https://github.com/weechat/weechat/issues/850), [#122](https://github.com/weechat/weechat/issues/122))
- irc: add server option "usermode" ([#377](https://github.com/weechat/weechat/issues/377), [#820](https://github.com/weechat/weechat/issues/820))
- irc: add tag "self_msg" on self messages ([#840](https://github.com/weechat/weechat/issues/840))
- irc: evaluate content of server option "ssl_fingerprint" ([#858](https://github.com/weechat/weechat/issues/858))
- irc: change default value of option irc.network.lag_reconnect from 0 to 300 ([#818](https://github.com/weechat/weechat/issues/818))
- trigger: do not hide email in command `/msg nickserv register password email` ([#849](https://github.com/weechat/weechat/issues/849))

### Bug fixes

- core: fix deadlock when quitting after a signal SIGHUP/SIGQUIT/SIGTERM is received ([#32](https://github.com/weechat/weechat/issues/32))
- core: fix display of empty lines in search mode ([#829](https://github.com/weechat/weechat/issues/829))
- api: fix crash in function string_expand_home when the HOME environment variable is not set ([#827](https://github.com/weechat/weechat/issues/827))
- exec: fix memory leak in display of process output
- irc: fix option `-temp` in command `/server` ([#880](https://github.com/weechat/weechat/issues/880))
- irc: fix close of server channels which are waiting for the JOIN when the server buffer is closed ([#873](https://github.com/weechat/weechat/issues/873))
- irc: fix buffer switching on manual join for forwarded channels ([#876](https://github.com/weechat/weechat/issues/876))
- irc: add missing tags on CTCP message sent
- lua: fix integers returned in Lua ≥ 5.3 ([#834](https://github.com/weechat/weechat/issues/834))
- relay: make HTTP headers case-insensitive for WebSocket connections ([#888](https://github.com/weechat/weechat/issues/888))
- relay: set status to "authentication failed" and close immediately connection in case of authentication failure in weechat and irc protocols ([#825](https://github.com/weechat/weechat/issues/825))
- script: reload a script after upgrade only if it was loaded, set autoload only if the script was auto-loaded ([#855](https://github.com/weechat/weechat/issues/855))

### Build

- core, irc, xfer: fix compilation on macOS (add link with resolv) ([#276](https://github.com/weechat/weechat/issues/276))
- core: add build of xz package with make dist (CMake)
- tests: fix compilation of tests on FreeBSD 11.0

## Version 1.6 (2016-10-02)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add optional argument `lowest`, `highest` or level mask in command `/input hotlist_clear`
- core: add option `cycle` in command `/buffer`
- core, irc, xfer: display more information on memory allocation errors ([#573](https://github.com/weechat/weechat/issues/573))
- api: add "extra" argument to evaluate extra variables in function string_eval_expression ([#534](https://github.com/weechat/weechat/issues/534))
- api: remove functions printf_date and printf_tags
- irc: rename server options "default_msg_{kick|part|quit}" to "msg_{kick|part|quit}", evaluate them
- relay: add option relay.network.allow_empty_password ([#735](https://github.com/weechat/weechat/issues/735))
- relay: allow escape of comma in command "init" (weechat protocol) ([#730](https://github.com/weechat/weechat/issues/730))
- trigger: add support for one-time triggers ([#399](https://github.com/weechat/weechat/issues/399), [#509](https://github.com/weechat/weechat/issues/509))

### Bug fixes

- core, irc, xfer: refresh domain name and name server addresses before connection to servers (fix connection to servers after suspend mode) ([#771](https://github.com/weechat/weechat/issues/771))
- api: fix return of function string_match when there are multiple masks in the string ([#812](https://github.com/weechat/weechat/issues/812))
- api: fix crash in function network_connect_to if address is NULL
- api: fix connection to servers with hook_connect on Windows 10 with Windows subsystem for Linux ([#770](https://github.com/weechat/weechat/issues/770))
- api: fix crash in function string_split_command when the separator is not a semicolon ([#731](https://github.com/weechat/weechat/issues/731))
- irc: fix socket leak in connection to server ([#358](https://github.com/weechat/weechat/issues/358), [#801](https://github.com/weechat/weechat/issues/801))
- irc: fix display of service notice mask (message 008) ([#429](https://github.com/weechat/weechat/issues/429))
- irc: fix NULL pointer dereference in 734 command callback ([#738](https://github.com/weechat/weechat/issues/738))
- relay: return an empty hdata when the requested hdata or pointer is not found ([#767](https://github.com/weechat/weechat/issues/767))
- xfer: fix crash on DCC send if option xfer.file.auto_accept_nicks is set ([#781](https://github.com/weechat/weechat/issues/781))

### Documentation

- switch to asciidoctor to build docs and man page ([#722](https://github.com/weechat/weechat/issues/722))

### Build

- python: add detection of Python 3.5

## Version 1.5 (2016-05-01)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: evaluate content of option "weechat.look.item_time_format" ([#791](https://github.com/weechat/weechat/issues/791))
- core: change default value of option weechat.look.nick_color_hash to "djb2"
- core: move nick coloring from irc plugin to core, move options irc.look.nick_color_force, irc.look.nick_color_hash and irc.look.nick_color_stop_chars to core, add info "nick_color" and "nick_color_name", deprecate info "irc_nick_color" and "irc_color_name" ([#262](https://github.com/weechat/weechat/issues/262))
- core: move irc bar item "away" to core, move options irc.look.item_away_message and irc.color.item_away to core ([#692](https://github.com/weechat/weechat/issues/692))
- api: add support of functions in hook_process
- api: add pointer in callbacks used in scripting API ([#406](https://github.com/weechat/weechat/issues/406))
- irc: add option irc.network.sasl_fail_unavailable ([#600](https://github.com/weechat/weechat/issues/600), [#697](https://github.com/weechat/weechat/issues/697))
- irc: add multiple targets and support of `-server` in command `/ctcp` ([#204](https://github.com/weechat/weechat/issues/204), [#493](https://github.com/weechat/weechat/issues/493))
- trigger: add "recover" in default triggers cmd_pass/msg_auth, and "regain" in default trigger "msg_auth" ([#511](https://github.com/weechat/weechat/issues/511))

### Internationalization

- add Portuguese translations

### Bug fixes

- core: fix nick coloring when stop chars and a forced color are used: first remove chars then look for forced color
- core: check that pointers received in arguments are not NULL in buffers and windows functions
- core: fix truncation of buffer names in hotlist ([#668](https://github.com/weechat/weechat/issues/668))
- core: fix update of window title under Tmux ([#685](https://github.com/weechat/weechat/issues/685))
- api: fix number of arguments returned by function string_split when keep_eol is 2 and the string ends with separators
- irc: fix first message displayed in raw buffer when the message is modified by a modifier ([#719](https://github.com/weechat/weechat/issues/719))
- irc: add missing completion "*" for target in command `/msg`
- irc: fix `/msg` command with multiple targets including "*"
- lua: fix crash when a lua function doesn't return a value and a string was expected ([#718](https://github.com/weechat/weechat/issues/718))
- relay: do not execute any command received in a PRIVMSG message from an irc relay client ([#699](https://github.com/weechat/weechat/issues/699))
- relay: fix the max number of clients connected on a port, allow value 0 for "no limit" ([#669](https://github.com/weechat/weechat/issues/669))
- relay: fix decoding of multiple frames in a single websocket message, send PONG on PING received in a websocket frame ([#675](https://github.com/weechat/weechat/issues/675))
- relay: fix command "input" received from clients with only spaces in content of message (weechat protocol) ([#663](https://github.com/weechat/weechat/issues/663))
- script: force refresh of scripts buffer after download of scripts list ([#693](https://github.com/weechat/weechat/issues/693))
- xfer: fix DCC file received when the terminal is resized ([#677](https://github.com/weechat/weechat/issues/677), [#680](https://github.com/weechat/weechat/issues/680))

### Build

- python: fix detection of Python shared libraries ([#676](https://github.com/weechat/weechat/issues/676))
- ruby: add detection of Ruby 2.3 ([#698](https://github.com/weechat/weechat/issues/698))

## Version 1.4 (2016-01-10)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add a parent name in options, display inherited values if null in `/set` output, add option weechat.color.chat_value_null ([#629](https://github.com/weechat/weechat/issues/629))
- core: add tag "term_warning" in warnings about wrong $TERM on startup
- core: add option weechat.look.paste_auto_add_newline ([#543](https://github.com/weechat/weechat/issues/543))
- core: display a more explicit error when a filter fails to be added ([#522](https://github.com/weechat/weechat/issues/522))
- api: add function string_hex_dump
- api: add argument "length" in function utf8_is_valid
- alias: display completion in `/alias list` ([#518](https://github.com/weechat/weechat/issues/518))
- fifo: add `/fifo` command
- irc: track real names using extended-join and WHO ([#351](https://github.com/weechat/weechat/issues/351))
- irc: add support of SNI (Server Name Indication) in SSL connection to IRC server ([#620](https://github.com/weechat/weechat/issues/620))
- irc: add support of "cap-notify" capability ([#182](https://github.com/weechat/weechat/issues/182), [#477](https://github.com/weechat/weechat/issues/477))
- irc: add command `/cap` ([#8](https://github.com/weechat/weechat/issues/8))
- irc: add hex dump of messages in raw buffer when debug is enabled for irc plugin (level 2 or more)
- irc: evaluate content of server option "addresses"
- irc: move option irc.network.alternate_nick into servers (irc.server.xxx.nicks_alternate) ([#633](https://github.com/weechat/weechat/issues/633))
- irc: use current channel and current server channels first in completions "irc_server_channels" and "irc_channels" ([task #12923](https://savannah.nongnu.org/task/?12923), [#260](https://github.com/weechat/weechat/issues/260), [#392](https://github.com/weechat/weechat/issues/392))
- logger: display system error when the log file cannot be written ([#541](https://github.com/weechat/weechat/issues/541))
- relay: add option relay.irc.backlog_since_last_message ([#347](https://github.com/weechat/weechat/issues/347))
- script: add option script.scripts.download_timeout
- script: add completion with languages and extensions, support search by language/extension in `/script search`

### Bug fixes

- core: fix execution of empty command name ("/" and "/ " are not valid commands)
- core: fix memory leak when using multiple `-d` or `-r` in command line arguments
- core: don't complain anymore about "tmux" and "tmux-256color" $TERM values when WeeChat is running under Tmux ([#519](https://github.com/weechat/weechat/issues/519))
- core: fix truncated messages after a word with a length of zero on screen (for example a zero width space: U+200B) ([bug #40985](https://savannah.nongnu.org/bugs/?40985), [#502](https://github.com/weechat/weechat/issues/502))
- api: fix handle of invalid escape in function string_convert_escaped_chars
- alias: do not allow slashes and spaces in alias name ([#646](https://github.com/weechat/weechat/issues/646))
- irc: fix channel forwarding when option irc.look.buffer_open_before_{autojoin|join} is on ([#643](https://github.com/weechat/weechat/issues/643))
- irc: add a missing colon before the password in PASS message, if the password has spaces or begins with a colon ([#602](https://github.com/weechat/weechat/issues/602))
- irc: fix charset decoding in incoming private messages ([#520](https://github.com/weechat/weechat/issues/520))
- irc: display the arrow before server name in raw buffer
- irc: fix display of messages sent to server in raw buffer
- irc: fix display of invalid UTF-8 chars in raw buffer
- relay: display the arrow before client id and protocol in raw buffer
- ruby: fix load of scripts requiring "uri" ([#433](https://github.com/weechat/weechat/issues/433))

### Documentation

- add Czech man page and quickstart guide ([#490](https://github.com/weechat/weechat/issues/490))

### Tests

- core: add a test to check if all plugins are loaded
- core: fix locale used to execute tests ([#631](https://github.com/weechat/weechat/issues/631))

### Build

- core: add scripts version.sh and build-debian.sh, separate stable from devel Debian packaging
- ruby: fix Ruby detection when pkg-config is not installed

## Version 1.3 (2015-08-16)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add completion "colors" ([#481](https://github.com/weechat/weechat/issues/481))
- core: start/stop search in buffer at current scroll position by default, add key `Ctrl`+`q` to stop search and reset scroll ([#76](https://github.com/weechat/weechat/issues/76), [#393](https://github.com/weechat/weechat/issues/393))
- core: add option weechat.look.key_grab_delay to set the default delay when grabbing a key with `Alt`+`k`
- core: add option weechat.look.confirm_upgrade ([#463](https://github.com/weechat/weechat/issues/463))
- core: add signal "signal_sighup"
- core: allow `Ctrl`+`c` to exit WeeChat when the passphrase is asked on startup ([#452](https://github.com/weechat/weechat/issues/452))
- core: allow pointer as list name in evaluation of hdata ([#450](https://github.com/weechat/weechat/issues/450))
- api: add support of evaluated sub-strings and current date/time in function string_eval_expression and command `/eval`
- api: add function string_eval_path_home
- alias: add options `add`, `addcompletion` and `del` in command `/alias`, remove command `/unalias` ([#458](https://github.com/weechat/weechat/issues/458))
- irc: add option irc.network.channel_encode ([#218](https://github.com/weechat/weechat/issues/218), [#482](https://github.com/weechat/weechat/issues/482))
- irc: add option irc.color.topic_current ([#475](https://github.com/weechat/weechat/issues/475))
- irc: evaluate content of server option "nicks"
- logger: evaluate content of option logger.file.path ([#388](https://github.com/weechat/weechat/issues/388))
- script: rename option script.scripts.dir to script.scripts.path, evaluate content of option ([#388](https://github.com/weechat/weechat/issues/388))
- relay: display value of HTTP header "X-Real-IP" for websocket connections ([#440](https://github.com/weechat/weechat/issues/440))
- xfer: evaluate content of options xfer.file.download_path and xfer.file.upload_path ([#388](https://github.com/weechat/weechat/issues/388))

### Bug fixes

- core: flush stdout/stderr after sending text directly on them (fix corrupted data sent to hook_process callback) ([#442](https://github.com/weechat/weechat/issues/442))
- core: allow execution of command `/input return` on a buffer which is not displayed in a window
- core: allow jump from current to previous buffer with default keys `Alt`+`j`, `01`…`99` ([#466](https://github.com/weechat/weechat/issues/466))
- core: fix crash if a file descriptor used in hook_fd is too high (> 1024 on Linux/BSD) ([#465](https://github.com/weechat/weechat/issues/465))
- core: fix display of invalid UTF-8 chars in bars
- core: fix bar item "scroll" after `/buffer clear` ([#448](https://github.com/weechat/weechat/issues/448))
- core: fix display of time in bare display when option weechat.look.buffer_time_format is set to empty string ([#441](https://github.com/weechat/weechat/issues/441))
- api: add missing function infolist_search_var in script API ([#484](https://github.com/weechat/weechat/issues/484))
- api: add missing function hook_completion_get_string in script API ([#484](https://github.com/weechat/weechat/issues/484))
- api: fix type of value returned by functions strcasestr, utf8_prev_char, utf8_next_char, utf8_add_offset and util_get_time_string
- api: fix type of value returned by function strcasestr
- fifo: fix send error on Cygwin when something is received in the pipe ([#436](https://github.com/weechat/weechat/issues/436))
- irc: fix update of lag item when the server lag changes
- irc: do not allow command `/query` with a channel name ([#459](https://github.com/weechat/weechat/issues/459))
- irc: decode/encode only text in IRC messages and not the headers ([bug #29886](https://savannah.nongnu.org/bugs/?29886), [#218](https://github.com/weechat/weechat/issues/218), [#451](https://github.com/weechat/weechat/issues/451))
- irc: fix crash with commands `/allchan`, `/allpv` and `/allserv` if the executed command closes buffers ([#445](https://github.com/weechat/weechat/issues/445))
- irc: do not open auto-joined channels buffers when option "-nojoin" is used in command `/connect` (even if the option irc.look.buffer_open_before_autojoin is on)
- irc: fix errors displayed on WHOX messages received ([#376](https://github.com/weechat/weechat/issues/376))
- xfer: fix crash if the DCC file socket number is too high (> 1024 on Linux/BSD) ([#465](https://github.com/weechat/weechat/issues/465))
- xfer: fix parsing of DCC chat messages (handle "\r\n" at the end of messages) ([#425](https://github.com/weechat/weechat/issues/425), [#426](https://github.com/weechat/weechat/issues/426))

### Documentation

- replace PREFIX with CMAKE_INSTALL_PREFIX in CMake instructions ([#354](https://github.com/weechat/weechat/issues/354))

### Build

- lua: add detection of Lua 5.3
- ruby: add detection of Ruby 2.2

## Version 1.2 (2015-05-10)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add signals "signal_sigterm" and "signal_sigquit" ([#114](https://github.com/weechat/weechat/issues/114))
- core: use environment variable WEECHAT_HOME on startup ([#391](https://github.com/weechat/weechat/issues/391))
- core: add options weechat.look.quote_{nick_prefix|nick_suffix|time_format} to customize quoted messages in cursor mode ([#403](https://github.com/weechat/weechat/issues/403))
- core: add a welcome message on first WeeChat run ([#318](https://github.com/weechat/weechat/issues/318))
- core: add options weechat.look.word_chars_{highlight|input} ([#55](https://github.com/weechat/weechat/issues/55), [task #9459](https://savannah.nongnu.org/task/?9459))
- core: remove WeeChat version from config files ([#407](https://github.com/weechat/weechat/issues/407))
- core: display a warning on startup if the locale cannot be set ([#373](https://github.com/weechat/weechat/issues/373))
- core: allow "*" as plugin name in command `/plugin reload` to reload all plugins with options
- core: add option `-s` in command `/eval` to split expression before evaluating it (no more split by default) ([#324](https://github.com/weechat/weechat/issues/324))
- core: add priority in plugins to initialize them in order
- api: add support of environment variables in function string_eval_expression and command `/eval`
- api: add support of full color option name in functions color and string_eval_expression and in command `/eval`
- api: add "_chat_line" (line pointer) in hashtable of hook_focus
- irc: add support of "account-notify" capability ([#11](https://github.com/weechat/weechat/issues/11), [#246](https://github.com/weechat/weechat/issues/246))
- irc: add support of "ecdsa-nist256p-challenge" SASL mechanism ([#251](https://github.com/weechat/weechat/issues/251))
- irc: display a warning when the option irc.look.display_away is set to "channel"
- irc: optimize search of a nick in nicklist (up to 3x faster)
- irc: add support of SHA-256 and SHA-512 algorithms in server option "ssl_fingerprint" ([#281](https://github.com/weechat/weechat/issues/281))
- irc: add option `-noswitch` in command `/query` ([#394](https://github.com/weechat/weechat/issues/394))
- irc: format message 008 (RPL_SNOMASK) ([#144](https://github.com/weechat/weechat/issues/144))
- irc: remove server "freenode" from default config file ([#309](https://github.com/weechat/weechat/issues/309))
- javascript: new script plugin for JavaScript

### Bug fixes

- core: add missing completions in command `/input`
- guile: fix value returned in case of error in functions: config_option_reset, config_color, config_color_default, config_write, config_read, config_reload, hook_command, buffer_string_replace_local_var, command
- irc: fix color of new nick in nick changes messages when option irc.look.color_nicks_in_server_messages is off
- irc: fix crash when setting an invalid regex with `/list -re` during a `/list` server response ([#412](https://github.com/weechat/weechat/issues/412))
- irc: fix display of PART messages on channels with +a (anonymous flag) ([#396](https://github.com/weechat/weechat/issues/396))
- irc: remove useless rename of channel buffer on JOIN received with different case ([#336](https://github.com/weechat/weechat/issues/336))
- irc: fix completion of commands `/allchan` and `/allpv`
- lua: fix wrong argument usage in functions nicklist_remove_group, nicklist_remove_nick and nicklist_remove_all ([#346](https://github.com/weechat/weechat/issues/346))
- lua: fix value returned in case of error in functions: config_option_reset, config_string, config_string_default, config_color, config_color_default, config_write, config_read, config_reload, hook_modifier_exec, buffer_string_replace_local_var, nicklist_group_set, nicklist_nick_set, command, upgrade_read, upgrade_close
- relay: fix up/down keys on relay buffer ([#335](https://github.com/weechat/weechat/issues/335))
- relay: remove v4-mapped addresses in `/help relay.network.allowed_ips` ([#325](https://github.com/weechat/weechat/issues/325))
- perl: fix value returned in case of error in functions: config_option_reset, config_color, config_color_default, config_write, config_read, config_reload, buffer_string_replace_local_var, command
- python: fix value returned in case of error in functions: config_option_reset, config_color, config_color_default, config_write, config_read, config_reload, config_is_set_plugin, buffer_get_string, buffer_string_replace_local_var, nicklist_group_get_string, nicklist_nick_get_string, command, hdata_time
- python: fix name of function "bar_update" in case of error
- python: fix restore of old interpreter when a function is not found in the script
- ruby: fix crash on `/plugin reload` ([#364](https://github.com/weechat/weechat/issues/364))
- ruby: fix value returned in case of error in functions: config_option_reset, config_color, config_color_default, config_write, config_read, config_reload, buffer_string_replace_local_var, command
- script: fix state of script plugins when list of scripts has not been downloaded
- scripts: reset current script pointer when load of script fails in python/perl/ruby/lua/tcl plugins
- scripts: fix return code of function bar_set in python/perl/ruby/lua/tcl/guile plugins
- scripts: fix type of value returned by function hdata_time (from string to long integer) in perl/ruby/lua/tcl/guile plugins
- tcl: fix value returned in case of error in functions: mkdir_home, mkdir, mkdir_parents, config_option_reset, config_color, config_color_default, config_write, config_read, config_reload, print_date_tags, buffer_string_replace_local_var, command, infolist_new_item, infolist_new_var_integer, infolist_new_var_string, infolist_new_var_pointer, infolist_new_var_time, upgrade_write_object, upgrade_read, upgrade_close
- trigger: do not hook anything if the trigger is disabled ([#405](https://github.com/weechat/weechat/issues/405))

### Documentation

- add Russian man page

## Version 1.1.1 (2015-01-25)

### Bug fixes

- core: fix crash when a root bar has conditions different from active/inactive/nicklist ([#317](https://github.com/weechat/weechat/issues/317))
- irc: don't close channel buffer on second `/part` when option irc.look.part_closes_buffer is off ([#313](https://github.com/weechat/weechat/issues/313))
- irc: fix `/join` on a channel buffer opened with autojoin but which failed to join
- irc: send QUIT to server and no PART for channels when the server buffer is closed ([#294](https://github.com/weechat/weechat/issues/294))
- irc: fix order of channel buffers opened when option irc.look.server_buffer is set to "independent", irc.look.buffer_open_before_autojoin to "on" and irc.look.new_channel_position to "near_server" ([#303](https://github.com/weechat/weechat/issues/303))
- irc: fix crash in buffer close when server name is the same as a channel name ([#305](https://github.com/weechat/weechat/issues/305))

### Build

- core: fix random error when creating symbolic link weechat-curses on make install with CMake ([bug #40313](https://savannah.nongnu.org/bugs/?40313))

## Version 1.1 (2015-01-11)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add option weechat.completion.command_inline ([task #12491](https://savannah.nongnu.org/task/?12491))
- core: add bar item "mouse_status", new options weechat.look.item_mouse_status and weechat.color.status_mouse ([#247](https://github.com/weechat/weechat/issues/247))
- core: add signals "mouse_enabled" and "mouse_disabled" ([#244](https://github.com/weechat/weechat/issues/244))
- core: add hide of chars in string in evaluation of expressions
- core: add arraylists, improve speed of completions (about 50x faster)
- core: allow incomplete commands if unambiguous, new option weechat.look.command_incomplete ([task #5419](https://savannah.nongnu.org/task/?5419))
- core: check bar conditions in root bars and on each update of a bar item
- core: fully evaluate commands bound to keys in cursor and mouse contexts
- core: move bar item "scroll" between buffer name and lag in default bar items of status bar
- api: add regex replace feature in function string_eval_expression
- api: send value returned by command callback in function command, remove WeeChat error after command callback if return code is WEECHAT_RC_ERROR
- api: use microseconds instead of milliseconds in functions util_timeval_diff and util_timeval_add
- irc: add option `reorder` in command `/server` ([#229](https://github.com/weechat/weechat/issues/229))
- irc: open channel buffers before the JOIN is received from server (autojoin and manual joins), new options irc.look.buffer_open_before_{autojoin|join} ([#216](https://github.com/weechat/weechat/issues/216))
- irc: add server option "sasl_fail" (continue/reconnect/disconnect if SASL fails) ([#265](https://github.com/weechat/weechat/issues/265), [task #12204](https://savannah.nongnu.org/task/?12204))
- irc: add support for color codes 16-99 in IRC messages ([#228](https://github.com/weechat/weechat/issues/228)), add infolist "irc_color_weechat"
- irc: add support of "extended-join" capability ([#143](https://github.com/weechat/weechat/issues/143), [#212](https://github.com/weechat/weechat/issues/212))
- irc: display own nick changes in server buffer ([#188](https://github.com/weechat/weechat/issues/188))
- irc: disable creation of temporary servers by default with command `/connect`, new option irc.look.temporary_servers
- irc: disable SSLv3 by default in server option "ssl_priorities" ([#248](https://github.com/weechat/weechat/issues/248))
- irc: automatically add current channel in command `/samode` ([#241](https://github.com/weechat/weechat/issues/241))
- irc: add tag "nick_xxx" in invite messages
- relay: add options `stop` and `restart` in command `/relay`
- relay: add option relay.network.ssl_priorities ([#234](https://github.com/weechat/weechat/issues/234))
- relay: add host in sender for IRC backlog PRIVMSG messages sent to clients
- script: add option script.scripts.url_force_https ([#253](https://github.com/weechat/weechat/issues/253))
- trigger: evaluate and replace regex groups at same time, new format for regex option in triggers (incompatible with version 1.0) ([#224](https://github.com/weechat/weechat/issues/224))
- trigger: add option `restore` in command `/trigger`
- trigger: add `${tg_displayed}` in conditions of default trigger "beep"

### Bug fixes

- core: fix display bug when scrolling in buffer on a filtered line ([#240](https://github.com/weechat/weechat/issues/240))
- core: send mouse code only one time to terminal with command `/mouse enable|disable|toggle`
- core: fix buffer property "lines_hidden" when merging buffers or when a line is removed from a buffer ([#226](https://github.com/weechat/weechat/issues/226))
- core: display time in bare display only if option weechat.look.buffer_time_format is not an empty string
- core: fix translation of message displayed after `/upgrade`
- api: fix truncated process output in hook_process ([#266](https://github.com/weechat/weechat/issues/266))
- api: fix crash when reading config options with NULL value ([#238](https://github.com/weechat/weechat/issues/238))
- irc: defer the auto-connection to servers with a timer ([#279](https://github.com/weechat/weechat/issues/279), [task #13038](https://savannah.nongnu.org/task/?13038))
- irc: add missing server options "sasl_timeout" and "notify" in output of `/server listfull`
- irc: use option irc.look.nick_mode_empty to display nick prefix in bar item "input_prompt"
- irc: remove IRC color codes from buffer title in channels ([#237](https://github.com/weechat/weechat/issues/237))
- irc: fix completion of commands `/msg`, `/notice` and `/query`
- irc: fix translation of CTCP PING reply ([#137](https://github.com/weechat/weechat/issues/137))
- relay: wait for message CAP END before sending join of channels and backlog to the client ([#223](https://github.com/weechat/weechat/issues/223))
- relay: send messages "_buffer_localvar_*" and "_buffer_type_changed" with sync "buffers" ([#191](https://github.com/weechat/weechat/issues/191))
- relay: don't remove relay from config when the binding fails ([#225](https://github.com/weechat/weechat/issues/225))
- relay: use comma separator in option relay.irc.backlog_tags, check the value of option when it is changed with `/set`
- relay: remove "::ffff:" from IPv4-mapped IPv6 client address ([#111](https://github.com/weechat/weechat/issues/111))
- trigger: fix memory leak when allocating a new trigger with several regex
- xfer: fix freeze when accepting DCC ([#160](https://github.com/weechat/weechat/issues/160), [#174](https://github.com/weechat/weechat/issues/174))
- xfer: bind to wildcard address when sending ([#173](https://github.com/weechat/weechat/issues/173))

### Build

- core: fix compilation of man pages with autotools in source directory
- core: fix compilation of plugins with CMake ≥ 3.1 ([#287](https://github.com/weechat/weechat/issues/287))
- lua: add detection of Lua 5.2
- python: fix Python detection with Homebrew ([#217](https://github.com/weechat/weechat/issues/217))
- tests: fix compilation of tests with clang ([#275](https://github.com/weechat/weechat/issues/275))

## Version 1.0.1 (2014-09-28)

### Bug fixes

- core: fix crash on buffer close when option weechat.look.hotlist_remove is set to "merged" ([#199](https://github.com/weechat/weechat/issues/199))
- core: fix highlight of IRC action messages when option irc.look.nick_mode is set to "action" or "both" ([#206](https://github.com/weechat/weechat/issues/206))
- core: fix compilation of plugin API functions (macros) when compiler optimizations are enabled ([#200](https://github.com/weechat/weechat/issues/200))
- core: fix window/buffer pointers used in command `/eval`
- core: fix modifier "weechat_print": discard only one line when several lines are displayed in same message ([#171](https://github.com/weechat/weechat/issues/171))
- api: fix bug in function hdata_move when absolute value of count is greater than 1
- aspell: fix crash with command `/aspell addword` if no word is given ([#164](https://github.com/weechat/weechat/issues/164), [#165](https://github.com/weechat/weechat/issues/165))
- irc: fix display of channel exception list (348) with 6 arguments (date missing)
- irc: fix type of value stored in hashtable when joining a channel ([#211](https://github.com/weechat/weechat/issues/211))
- relay: fix send of signals "relay_client_xxx" ([#214](https://github.com/weechat/weechat/issues/214))
- script: fix crash on `/script update` if a script detail is displayed in buffer ([#177](https://github.com/weechat/weechat/issues/177))
- trigger: do not allow any changes on a trigger when it is currently running ([#189](https://github.com/weechat/weechat/issues/189))
- trigger: fix regex used in default triggers to hide passwords ("\S" is not supported on *BSD) ([#172](https://github.com/weechat/weechat/issues/172))

### Tests

- core: fix memory leak in tests launcher

### Build

- aspell: fix compilation with Enchant < 1.6.0 ([#192](https://github.com/weechat/weechat/issues/192))
- guile: fix compilation with Guile < 2.0.4 ([#198](https://github.com/weechat/weechat/issues/198))
- perl: fix detection of Perl ≥ 5.20 with autotools
- tests: fix build of tests when the build directory is outside source tree ([#178](https://github.com/weechat/weechat/issues/178))

## Version 1.0 (2014-08-15)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: display a warning on startup if $TERM does not start with "screen" under Screen/Tmux
- core: add option weechat.color.status_nicklist_count ([#109](https://github.com/weechat/weechat/issues/109), [#110](https://github.com/weechat/weechat/issues/110))
- core: add option `env` in command `/set` (manage environment variables)
- core: add bar item "buffer_short_name" ([task #10882](https://savannah.nongnu.org/task/?10882))
- core: add option `send` in command `/input` (send text to a buffer)
- core: add support of negated tags in filters (with "!") ([#72](https://github.com/weechat/weechat/issues/72), [#74](https://github.com/weechat/weechat/issues/74))
- core: add hidden buffers, add options hide/unhide in command `/buffer`
- core: add default key `Alt`+`-` (toggle filters in current buffer) ([#17](https://github.com/weechat/weechat/issues/17))
- core: add non-active merged buffers with activity in hotlist (if another merged buffer is zoomed) ([task #12845](https://savannah.nongnu.org/task/?12845))
- core: add text search in buffers with free content ([task #13051](https://savannah.nongnu.org/task/?13051))
- core: add buffer property "clear"
- core: add option weechat.look.hotlist_add_conditions, remove option weechat.look.hotlist_add_buffer_if_away
- core: add option weechat.look.hotlist_remove ([#99](https://github.com/weechat/weechat/issues/99))
- core: add options `-beep` and `-current` in command `/print`
- core: add bare display mode for easy text selection and click on URLs, new key: `Alt`+`l` (lower `L`), new option "bare" in command `/window`, new options: weechat.look.bare_display_exit_on_input and weechat.look.bare_display_time_format
- core: add signals "key_combo_{default|search|cursor}"
- core: add terabyte unit for size displayed
- core: display a warning in case of inconsistency between the options weechat.look.save_{config|layout}_on_exit
- core: add option `-mask` in command `/unset` ([#112](https://github.com/weechat/weechat/issues/112))
- core: set option weechat.look.buffer_search_where to prefix_message by default
- core: mute all buffers by default in command `/mute` (replace option -all by -core)
- api: allow value "-1" for property "hotlist" in function buffer_set (to remove a buffer from hotlist)
- api: add option "buffer_flush" in function hook_process_hashtable
- api: add support of case-insensitive search and search by buffer full name in function buffer_search ([bug #34318](https://savannah.nongnu.org/bugs/?34318))
- api: add option "detached" in function hook_process_hashtable
- api: add option "signal" in function hook_set to send a signal to the child process
- api: add support of nested variables in function string_eval_expression and command `/eval` ([#35](https://github.com/weechat/weechat/issues/35))
- api: add support of escaped strings with format `${esc:xxx}` or `${\xxx}` in function string_eval_expression and command `/eval`
- api: add functions hashtable_dup, string_replace_regex, string_split_shell, string_convert_escaped_chars
- api: add integer return code for functions hook_{signal|hsignal}_send
- api: add argument "flags" in function hdata_new_list
- api: allow wildcard "*" inside the mask in function string_match
- api: allow negative value for y in function printf_y
- alias: add default alias `msgbuf` (send text to a buffer)
- exec: add exec plugin: new command `/exec` and file exec.conf
- irc: add bar item "irc_nick_modes" ([#71](https://github.com/weechat/weechat/issues/71))
- irc: add support of message 324 (channel modes) in option irc.look.display_join_message ([#75](https://github.com/weechat/weechat/issues/75))
- irc: add option irc.look.join_auto_add_chantype ([#65](https://github.com/weechat/weechat/issues/65))
- irc: add tag with host ("host_xxx") in IRC messages displayed ([task #12018](https://savannah.nongnu.org/task/?12018))
- irc: add option irc.color.item_nick_modes ([#47](https://github.com/weechat/weechat/issues/47))
- irc: add support of "away-notify" capability ([#12](https://github.com/weechat/weechat/issues/12))
- irc: add command `/remove` ([#91](https://github.com/weechat/weechat/issues/91))
- irc: add command `/unquiet` ([#36](https://github.com/weechat/weechat/issues/36))
- irc: add command `/allpv` ([task #13111](https://savannah.nongnu.org/task/?13111))
- irc: display locally away status changes in private buffers (in addition to channels) ([#117](https://github.com/weechat/weechat/issues/117))
- irc: allow many fingerprints in server option ssl_fingerprint ([#49](https://github.com/weechat/weechat/issues/49))
- irc: rename option irc.look.item_channel_modes_hide_key to irc.look.item_channel_modes_hide_args, value is now a string ([task #12070](https://savannah.nongnu.org/task/?12070), [task #12163](https://savannah.nongnu.org/task/?12163), [#48](https://github.com/weechat/weechat/issues/48))
- irc: add value "+" for option irc.look.smart_filter_mode to use modes from server prefixes (this is now the default value) ([#90](https://github.com/weechat/weechat/issues/90))
- irc: allow "$ident" in option irc.network.ban_mask_default ([#18](https://github.com/weechat/weechat/issues/18))
- irc: evaluate content of server options "username" and "realname"
- irc: set option irc.network.autoreconnect_delay_max to 600 by default, increase max value to 604800 seconds (7 days)
- irc: set option irc.network.whois_double_nick to "off" by default
- relay: add messages "_buffer_cleared", "_buffer_hidden" and "_buffer_unhidden"
- relay: add info "relay_client_count" with optional status name as argument
- relay: add signals "relay_client_xxx" for client status changes ([#2](https://github.com/weechat/weechat/issues/2))
- relay: add option relay.network.clients_purge_delay
- rmodifier: remove plugin (replaced by trigger)
- script: set option script.scripts.cache_expire to 1440 by default
- trigger: add trigger plugin: new command `/trigger` and file trigger.conf

### Bug fixes

- core: fix zero-length malloc of an hashtable item with type "buffer"
- core: fix memory leak on `/upgrade` when file signature in upgrade file is invalid
- core: fix memory leak in completion of config options values
- core: fix memory leak when removing script files
- core: fix result of hash function (in hashtables) on 32-bit systems
- core: fix insert of mouse code in input line after a partial key combo ([#130](https://github.com/weechat/weechat/issues/130))
- core: check code point value in UTF-8 check function ([#108](https://github.com/weechat/weechat/issues/108))
- core: fix socks5 proxy for curl downloads ([#119](https://github.com/weechat/weechat/issues/119))
- core: display curl error after a failed download
- core: do not display content of passphrase on `/secure` buffer
- core: fix potential memory leak with infolists not freed in plugins ([debian #751108](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=751108))
- core: fix color display of last terminal color number + 1 ([#101](https://github.com/weechat/weechat/issues/101))
- core: add option "-buffer" in command `/command` ([#67](https://github.com/weechat/weechat/issues/67))
- core: fix restoration of core buffer properties after `/upgrade`
- core: fix `/buffer clear` with a name (don't clear all merged buffers with same number)
- core: fix evaluation of expression with regex: when a comparison char is in the regex and don't evaluate the regex itself ([#63](https://github.com/weechat/weechat/issues/63))
- core: close .upgrade files before deleting them after `/upgrade`
- core: fix refresh of bar item "buffer_zoom" on buffer switch
- core: fix reset of attributes in bars when "resetcolor" is used ([#41](https://github.com/weechat/weechat/issues/41))
- core: fix alignment of lines in merged buffers when options weechat.look.prefix_align and weechat.look.prefix_buffer_align are set to "none" ([#43](https://github.com/weechat/weechat/issues/43))
- core: quit WeeChat on signal SIGHUP, remove signal "signal_sighup"
- core: fix add of filter on macOS when regex for message is empty (filter regex ending with "\t")
- core: check validity of buffer pointer when data is sent to a buffer (command/text from user and API function command)
- core: fix crash when buffer is closed during execution of multiple commands ([#27](https://github.com/weechat/weechat/issues/27))
- core: fix compilation on SmartOS ([bug #40981](https://savannah.nongnu.org/bugs/?40981), [#23](https://github.com/weechat/weechat/issues/23))
- core: add missing \0 at the end of stderr buffer in function hook_process
- core: fix highlight problem with "(?-i)" and upper case letters in option weechat.look.highlight ([#24](https://github.com/weechat/weechat/issues/24))
- core: fix detection of terminated process in function hook_process
- core: fix `/window scroll -N` on a buffer with free content
- core: fix recursive calls to function eval_expression
- core: save and restore mute state in command `/mute` ([bug #41748](https://savannah.nongnu.org/bugs/?41748))
- core: fix memory leak when removing a hdata
- core: fix memory leak in evaluation of sub-conditions
- core: fix memory leak in function gui_key_add_to_infolist (in case of insufficient memory)
- core: fix use of invalid pointer in function gui_bar_window_content_alloc (in case of insufficient memory)
- core: fix uninitialized value in function string_decode_base64
- core: fix memory leak and use of invalid pointer in split of string (in case of insufficient memory)
- core: fix potential NULL pointer in function gui_color_emphasize
- core: use same return code and message in all commands when arguments are wrong/missing
- core: allow empty arguments for command `/print`
- core: fix freeze/crash in GnuTLS ([bug #41576](https://savannah.nongnu.org/bugs/?41576))
- api: fix function string_decode_base64
- api: fix function string_format_size on 32-bit systems
- api: change type of arguments displayed/highlight in hook_print callback from string to integer (in scripts)
- alias: change default command for alias `/beep` to `/print -beep`
- guile: fix module used after unload of a script
- irc: fix memory leak in CTCP answer
- irc: fix duplicate sender name in display of wallops ([#142](https://github.com/weechat/weechat/issues/142), [#145](https://github.com/weechat/weechat/issues/145))
- irc: fix extract of channel in parser for JOIN/PART messages when there is a colon before the channel name ([#83](https://github.com/weechat/weechat/issues/83))
- irc: fix duplicate sender name in display of notice ([#87](https://github.com/weechat/weechat/issues/87))
- irc: fix refresh of buffer name in bar items after join/part/kick/kill ([#86](https://github.com/weechat/weechat/issues/86))
- irc: display message 936 (censored word) on channel instead of server buffer
- irc: make reason optional in command `/kill`
- irc: add alias `whois` for target buffer of messages 401/402 ([#54](https://github.com/weechat/weechat/issues/54))
- irc: fix truncated read on socket with SSL ([bug #41558](https://savannah.nongnu.org/bugs/?41558))
- irc: display output of CAP LIST in server buffer
- irc: fix colors in message with CTCP reply sent to another user
- irc: fix read of MODES server value when in commands `/op`, `/deop`, `/voice`, `/devoice`, `/halfop`, `/dehalfop`
- irc: fix parsing of nick in host when "!" is not found ([bug #41640](https://savannah.nongnu.org/bugs/?41640))
- lua: fix interpreter used after unload of a script
- perl: fix context used after unload of a script
- python: fix read of return value for callbacks returning an integer in Python 2.x ([#125](https://github.com/weechat/weechat/issues/125))
- python: fix interpreter used after unload of a script
- relay: fix memory leak during handshake on websocket
- relay: fix memory leak when receiving commands from client (weechat protocol)
- relay: fix crash when an IRC "MODE" command is received from client without arguments
- relay: fix number of bytes sent/received on 32-bit systems
- relay: fix crash when closing relay buffers ([#57](https://github.com/weechat/weechat/issues/57), [#78](https://github.com/weechat/weechat/issues/78))
- relay: check pointers received in hdata command to prevent crashes with bad pointers (WeeChat protocol)
- relay: remove warning on `/reload` of relay.conf when ports are defined
- relay: fix client disconnection on empty websocket frames received (PONG)
- relay: add support of Internet Explorer websocket ([#73](https://github.com/weechat/weechat/issues/73))
- relay: fix crash on `/upgrade` received from a client (weechat protocol)
- relay: fix freeze after `/upgrade` when many disconnected clients still exist
- relay: fix NULL pointer when reading buffer lines for irc backlog
- ruby: fix crash when trying to load a directory with `/ruby load`
- script: fix display of curl errors
- script: fix scroll on script buffer in the detailed view of script ([#6](https://github.com/weechat/weechat/issues/6))
- scripts: fix crash when a signal is received with type "int" and NULL pointer in signal_data
- xfer: fix problem with option xfer.file.auto_accept_nicks when the server name contains dots
- xfer: fix freeze/problems when sending empty files with DCC ([#53](https://github.com/weechat/weechat/issues/53))
- xfer: fix connection to remote host in DCC receive on macOS ([#25](https://github.com/weechat/weechat/issues/25))
- xfer: remove bind on xfer.network.own_ip ([#5](https://github.com/weechat/weechat/issues/5))

### Build

- core: fix CMake warning CMP0007 on "make uninstall" ([bug #41528](https://savannah.nongnu.org/bugs/?41528))
- core: use glibtoolize on macOS (autotools) ([#22](https://github.com/weechat/weechat/issues/22))
- ruby: add detection of Ruby 2.1

### Tests

- core: add unit tests using CppUTest ([#104](https://github.com/weechat/weechat/issues/104))

## Version 0.4.3 (2014-02-09)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add signals "signal_sighup" and "signal_sigwinch" (terminal resized)
- core: add command `/print`, add support of more escaped chars in command `/input insert`
- core: add option weechat.look.tab_width
- core: add completion "plugins_installed"
- core: add option weechat.look.window_auto_zoom, disable automatic zoom by default when terminal becomes too small for windows
- core: use "+" separator to make a logical "and" between tags in command `/filter`, option weechat.look.highlight_tags and buffer property "highlight_tags"
- core: add options weechat.look.buffer_auto_renumber and weechat.look.buffer_position, add option `renumber` in command `/buffer`, add bar item "buffer_last_number" ([task #12766](https://savannah.nongnu.org/task/?12766))
- core: add signal "buffer_cleared"
- core: add buffer property "day_change" to hide messages for the day change in specific buffers
- core: add option "libs" in command `/debug`
- core: add infos "term_width" and "term_height"
- core: add bar item "buffer_zoom", add signals "buffer_{zoomed|unzoomed}" ([patch #8204](https://savannah.nongnu.org/patch/?8204))
- core: add default keys `Alt`+`Home` / `Alt`+`End` (`meta2-1;3H` / `meta2-1;3F`) and `Alt`+`F11` / `Alt`+`F12` (`meta2-23;3~` / `meta2-24;3~`) for xterm
- core: add support of italic text (requires ncurses ≥ 5.9 patch 20130831)
- core: add options to customize default text search in buffers: weechat.look.buffer_search_{case_sensitive|force_default|regex|where}
- core: add support of UTF-8 chars in horizontal/vertical separators (options weechat.look.separator_{horizontal|vertical})
- core: add support of logical and/or for argument "tags" in function hook_print
- core: rename buffer property "highlight_tags" to "highlight_tags_restrict", new behavior for buffer property "highlight_tags" (force highlight on tags), rename option irc.look.highlight_tags to irc.look.highlight_tags_restrict
- core: rename options save/reset to store/del in command `/layout`
- core: replace default key `Ctrl`+`c`, `r` by `Ctrl`+`c`, `v` for reverse video in messages
- core: replace default key `Ctrl`+`c`, `u` by `Ctrl`+`c`, `_` for underlined text in messages
- core: rename option weechat.look.set_title to weechat.look.window_title, value is now a string (evaluated)
- core: set option weechat.look.paste_bracketed to "on" by default
- core: use one date format when day changes from day to day+1
- api: add function infolist_search_var
- api: add stdin options in functions hook_process_hashtable and hook_set to send data on stdin of child process, add function hook_set in script API ([task #10847](https://savannah.nongnu.org/task/?10847), [task #13031](https://savannah.nongnu.org/task/?13031))
- api: add hdata "buffer_visited"
- api: add support of infos with format `${info:name,arguments}` in function string_eval_expression and command `/eval`
- api: add support for C++ plugins
- alias: add default alias `/beep` to `/print -stderr \a`
- irc: add server option "ssl_fingerprint" ([task #12724](https://savannah.nongnu.org/task/?12724))
- irc: add option irc.look.smart_filter_mode ([task #12499](https://savannah.nongnu.org/task/?12499))
- irc: add option irc.network.ban_mask_default ([bug #26571](https://savannah.nongnu.org/bugs/?26571))
- irc: add option irc.network.lag_max
- irc: add option irc.look.notice_welcome_tags
- irc: add server option "default_msg_kick" to customize default kick/kickban message ([task #12777](https://savannah.nongnu.org/task/?12777))
- irc: use MONITOR instead of ISON for `/notify` when it is available on server ([task #11477](https://savannah.nongnu.org/task/?11477))
- relay: send backlog for irc private buffers
- xfer: add support of IPv6 for DCC chat/file ([patch #7992](https://savannah.nongnu.org/patch/?7992))
- xfer: add option xfer.file.auto_check_crc32 ([patch #7963](https://savannah.nongnu.org/patch/?7963))

### Bug fixes

- core: fix hotlist problems after apply of a layout ([bug #41481](https://savannah.nongnu.org/bugs/?41481))
- core: fix crash when creating two bars with same name but different case ([bug #41418](https://savannah.nongnu.org/bugs/?41418))
- core: fix display of read marker when all buffer lines are unread and that option weechat.look.read_marker_always_show is on
- core: fix memory leak in regex matching when evaluating expression
- core: fix crash in `/eval` when config option has a NULL value
- core: fix crash with hdata_update on shared strings, add hdata type "shared_string" ([bug #41104](https://savannah.nongnu.org/bugs/?41104))
- core: fix text emphasis with wide chars on screen like Japanese ([patch #8253](https://savannah.nongnu.org/patch/?8253))
- core: remove option on `/unset` of plugin description option (plugins.desc.xxx) ([bug #40768](https://savannah.nongnu.org/bugs/?40768))
- core: fix random crash when closing a buffer
- core: fix crash on `/buffer close core.weechat`
- core: apply color attributes when clearing a window ([patch #8236](https://savannah.nongnu.org/patch/?8236))
- core: fix truncated text when pasting several long lines ([bug #40210](https://savannah.nongnu.org/bugs/?40210))
- core: create .conf file with default options only if the file does not exist (and not on read error with existing file)
- core: fix highlight on action messages: skip the nick at beginning to prevent highlight on it ([bug #40516](https://savannah.nongnu.org/bugs/?40516))
- core: fix bind of keys in cursor/mouse context when key starts with "@" (remove the warning about unsafe key)
- core: fix truncated prefix when filters are toggled ([bug #40204](https://savannah.nongnu.org/bugs/?40204))
- api: fix read of arrays in hdata functions hdata_<type> ([bug #40354](https://savannah.nongnu.org/bugs/?40354))
- aspell: fix detection of nicks with non-alphanumeric chars
- guile: disable guile gmp allocator (fix crash on unload of relay plugin) ([bug #40628](https://savannah.nongnu.org/bugs/?40628))
- irc: clear the GnuTLS session in all cases after SSL connection error
- irc: do not display names by default when joining a channel ([task #13045](https://savannah.nongnu.org/task/?13045))
- irc: display PONG answer when resulting from manual `/ping` command
- irc: fix time parsed in tag of messages on Cygwin
- irc: use statusmsg from message 005 to check prefix char in status notices/messages
- irc: remove display of channel in channel notices, display "PvNotice" for channel welcome notices
- irc: fix ignore on a host without nick
- irc: use color code 0x1F (`ctrl-_`) for underlined text in input line (same code as messages) ([bug #40756](https://savannah.nongnu.org/bugs/?40756))
- irc: use color code 0x16 (`ctrl-v`) for reverse video in messages
- irc: use option irc.network.colors_send instead of irc.network.colors_receive when displaying messages sent by commands `/away`, `/me`, `/msg`, `/notice`, `/query`
- irc: fix memory leak when checking the value of ssl_priorities option in servers
- irc: fix memory leak when a channel is deleted
- irc: fix groups in channel nicklist when reconnecting to a server that supports more nick prefixes than the previously connected server
- irc: fix auto-switch to channel buffer when doing `/join channel` (without "#")
- logger: fix memory leaks in backlog
- logger: replace backslashes in name by logger replacement char under Cygwin ([bug #41207](https://savannah.nongnu.org/bugs/?41207))
- lua: fix crash on calls to callbacks during load of script
- python: fix load of scripts with Python ≥ 3.3
- relay: fix memory leak on unload of relay plugin
- ruby: fix ruby init with Ruby ≥ 2.0 ([bug #41115](https://savannah.nongnu.org/bugs/?41115))
- scripts: fix script interpreter used after register during load of script in python/perl/ruby/lua/guile plugins ([bug #41345](https://savannah.nongnu.org/bugs/?41345))
- xfer: use same infolist for hook and signals ([patch #7974](https://savannah.nongnu.org/patch/?7974))

### Documentation

- add French developer's guide and relay protocol
- add Japanese plugin API reference and developer's guide
- add Polish man page and user's guide

### Build

- core: fix installation of weechat-plugin.h with autotools ([patch #8305](https://savannah.nongnu.org/patch/?8305))
- core: fix compilation on Android ([bug #41420](https://savannah.nongnu.org/bugs/?41420), [patch #8301](https://savannah.nongnu.org/patch/?8301), [bug #41434](https://savannah.nongnu.org/bugs/?41434))
- lua: fix detection of Lua 5.2 in autotools ([patch #8270](https://savannah.nongnu.org/patch/?8270))
- ruby: add detection and fix compilation with Ruby 2.0 ([patch #8209](https://savannah.nongnu.org/patch/?8209))

## Version 0.4.2 (2013-10-06)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: display day change message dynamically (do not store it as a line in buffer), split option weechat.look.day_change_time_format into two options weechat.look.day_change_message_{1date|2dates}, new option weechat.color.chat_day_change ([task #12775](https://savannah.nongnu.org/task/?12775))
- core: add syntax "@buffer:item" in bar items to force the buffer used when displaying the bar item ([task #12717](https://savannah.nongnu.org/task/?12717))
- core: add search of regular expression in buffer, don't reset search type on a new search, select where to search (messages/prefixes), add keys in search context: `Alt`+`c` (case (in)sensitive search), `Tab` (search in messages/prefixes)
- core: add text emphasis in messages when searching text in buffer, new options: weechat.look.emphasized_attributes, weechat.color.emphasized, weechat.color.emphasized_bg
- core: add secured data (encryption of passwords or private data): add new command `/secure` and new file sec.conf ([task #7395](https://savannah.nongnu.org/task/?7395))
- core: rename binary and man page from "weechat-curses" to "weechat" ([task #11027](https://savannah.nongnu.org/task/?11027))
- core: add option `-o` in command `/color`
- core: add option `scroll_beyond_end` for command `/window` ([task #6745](https://savannah.nongnu.org/task/?6745))
- core: add options weechat.look.hotlist_prefix and weechat.look.hotlist_suffix ([task #12730](https://savannah.nongnu.org/task/?12730))
- core: add option weechat.look.key_bind_safe
- core: add option weechat.network.proxy_curl ([task #12651](https://savannah.nongnu.org/task/?12651))
- core: add "proxy" infolist and hdata
- core: add infolist "layout" and hdata "layout", "layout_buffer" and "layout_window"
- core: reduce memory used by using shared strings for nicklist and lines in buffers
- core: change color format for options weechat.look.buffer_time_format and weechat.look.prefix_{action|error|join|network|quit} from `${xxx}` to `${color:xxx}`
- core: optimize the removal of lines in buffers (a lot faster to clear/close buffers with lot of lines)
- core: set options weechat.look.color_inactive_{buffer|window} to "on" by default
- api: return hashtable item pointer in functions hashtable_set and hashtable_set_with_size
- api: add "callback_free_key" in hashtable
- api: add support of colors with format `${color:xxx}` in function string_eval_expression and command `/eval`
- api: add argument "options" in function string_eval_expression, add option `-c` in command `/eval` (to evaluate a condition)
- api: add new function strlen_screen
- aspell: rename option aspell.look.color to aspell.color.misspelled, add option aspell.color.suggestions
- aspell: add support of enchant library ([patch #6858](https://savannah.nongnu.org/patch/?6858))
- irc: add option irc.look.notice_welcome_redirect to automatically redirect channel welcome notices to the channel buffer
- irc: add support of wildcards in commands (de)op/halfop/voice, split IRC message sent if number of nicks is greater than server MODES (from message 005) ([task #9221](https://savannah.nongnu.org/task/?9221))
- irc: add option irc.look.pv_tags
- irc: add support of special variables $nick/$channel/$server in commands `/allchan` and `/allserv`
- irc: add option irc.look.nick_color_hash: hash algorithm to find nick color ([patch #8062](https://savannah.nongnu.org/patch/?8062))
- logger: add option `flush` in command `/logger`
- plugins: remove the demo plugin
- relay: add command "ping" in weechat protocol ([task #12689](https://savannah.nongnu.org/task/?12689))
- rmodifier: add option "missing" in command `/rmodifier`
- script: add info about things defined by script (like commands, options, ...) in the detailed view of script (`/script show`)
- scripts: add hdata with script callback
- xfer: add option xfer.look.pv_tags

### Bug fixes

- core: clear whole line before displaying content instead of clearing after the end of content ([bug #40115](https://savannah.nongnu.org/bugs/?40115))
- core: fix time displayed in status bar (it was one second late) ([bug #40097](https://savannah.nongnu.org/bugs/?40097))
- core: fix memory leak on unhook of a print hook (if using tags)
- core: fix computation of columns in output of `/help` (take care about size of time/buffer/prefix)
- core: fix random crash on `/buffer close` with a buffer number (or a range of buffers)
- core: fix priority of logical operators in evaluation of expression (AND takes precedence over the OR) and first evaluate sub-expressions between parentheses
- core: remove gap after read marker line when there is no bar on the right ([bug #39548](https://savannah.nongnu.org/bugs/?39548))
- core: use "/dev/null" for stdin in hook_process instead of closing stdin ([bug #39538](https://savannah.nongnu.org/bugs/?39538))
- core: fix char displayed at the intersection of three windows ([bug #39331](https://savannah.nongnu.org/bugs/?39331))
- core: fix crash in evaluation of expression when reading a string in hdata with a NULL value ([bug #39419](https://savannah.nongnu.org/bugs/?39419))
- core: fix display bugs with some UTF-8 chars that truncates messages displayed (for example U+26C4) ([bug #39201](https://savannah.nongnu.org/bugs/?39201))
- core: remove extra space after empty prefix (when prefix for action, error, join, network or quit is set to empty string) ([bug #39218](https://savannah.nongnu.org/bugs/?39218))
- core: fix random crash on mouse actions ([bug #39094](https://savannah.nongnu.org/bugs/?39094))
- core: fix line alignment when option weechat.look.buffer_time_format is set to empty string
- api: change type of hashtable key hash to unsigned long
- api: use pointer for infolist "hook" to return only one hook
- aspell: fix detection of word start/end when there are apostrophes or minus chars before/after word
- irc: fix reconnection to server using IPv6 ([bug #38819](https://savannah.nongnu.org/bugs/?38819), [bug #40166](https://savannah.nongnu.org/bugs/?40166))
- irc: replace default prefix modes "qaohvu" by the standard ones "ov" when PREFIX is not sent by server ([bug #39802](https://savannah.nongnu.org/bugs/?39802))
- irc: use 6697 as default port for SSL servers created with URL "ircs://" ([bug #39621](https://savannah.nongnu.org/bugs/?39621))
- irc: display number of ops/halfops/voices on channel join only for supported modes on server ([bug #39582](https://savannah.nongnu.org/bugs/?39582))
- irc: fix self nick color in server messages after nick is changed with `/nick` ([bug #39415](https://savannah.nongnu.org/bugs/?39415))
- irc: fix error message on `/invite` without arguments ([bug #39272](https://savannah.nongnu.org/bugs/?39272))
- irc: fix multiple nicks in command `/query` (separated by commas): open one buffer per nick
- lua: fix interpreter used in API functions ([bug #39470](https://savannah.nongnu.org/bugs/?39470))
- relay: fix decoding of websocket frames when there are multiple frames in a single message received (only the first one was decoded)
- relay: fix binding to an IP address ([bug #39119](https://savannah.nongnu.org/bugs/?39119))

### Documentation

- update man page and add translations (in French, German, Italian, and Japanese)

### Build

- core: add CA_FILE option in CMake and configure to setup default value of option weechat.network.gnutls_ca_file (default is "/etc/ssl/certs/ca-certificates.crt") ([task #12725](https://savannah.nongnu.org/task/?12725))
- core: disable build of doc by default, add CMake option "ENABLE_MAN" to compile man page (off by default)
- xfer: fix compilation on OpenBSD ([bug #39071](https://savannah.nongnu.org/bugs/?39071))

## Version 0.4.1 (2013-05-20)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: make nick prefix/suffix dynamic (not stored in the line): move options irc.look.nick_{prefix|suffix} to weechat.look.nick_{prefix|suffix} and options irc.color.nick_{prefix|suffix} to weechat.color.chat_nick_{prefix|suffix}, add new options weechat.look.prefix_align_more_after, weechat.look.prefix_buffer_align_more_after, logger.file.nick_{prefix|suffix} ([bug #37531](https://savannah.nongnu.org/bugs/?37531))
- core: add support of multiple layouts ([task #11274](https://savannah.nongnu.org/task/?11274))
- core: add signals nicklist_{group|nick}_removing and hsignals nicklist_{group|nick}_{added|removing|changed}
- core: add count for groups, nicks, and total in nicklist
- core: add option `dirs` in command `/debug`
- core: add signal "window_opened" ([task #12464](https://savannah.nongnu.org/task/?12464))
- core: allow read of array in hdata without using index
- api: add new function hdata_search
- api: add property "completion_freeze" for function buffer_set: do not stop completion when command line is updated
- aspell: add completion "aspell_dicts" (list of aspell installed dictionaries)
- aspell: add info "aspell_dict" (dictionaries used on a buffer)
- aspell: optimization on spellers to improve speed (save state by buffer)
- irc: add support of DH-AES SASL mechanism ([patch #8020](https://savannah.nongnu.org/patch/?8020))
- irc: add support of UHNAMES (capability "userhost-in-names") ([task #9353](https://savannah.nongnu.org/task/?9353))
- irc: add tag "irc_nick_back" for messages displayed in private buffer when a nick is back on server ([task #12576](https://savannah.nongnu.org/task/?12576))
- irc: add option irc.look.display_join_message ([task #10895](https://savannah.nongnu.org/task/?10895))
- irc: add option irc.look.pv_buffer: automatically merge private buffers (optionally by server) ([task #11924](https://savannah.nongnu.org/task/?11924))
- irc: hide passwords in commands or messages sent to nickserv (`/msg nickserv`) with new modifiers "irc_command_auth" and "irc_message_auth", remove option irc.look.hide_nickserv_pwd, add option irc.look.nicks_hide_password ([bug #38346](https://savannah.nongnu.org/bugs/?38346))
- irc: unmask smart filtered join if nick speaks in channel some minutes after the join, new option irc.look.smart_filter_join_unmask ([task #12405](https://savannah.nongnu.org/task/?12405))
- irc: rename option irc.network.lag_disconnect to irc.network.lag_reconnect, value is now a number of seconds
- relay: add message "_nicklist_diff" (differences between old and current nicklist)
- relay: add support of multiple servers on same port for irc protocol (the client must send the server in the "PASS" command)
- relay: add WebSocket server support (RFC 6455) for irc and weechat protocols, new option relay.network.websocket_allowed_origins
- relay: add options "buffers" and "upgrade" in commands sync/desync (weechat protocol)
- rmodifier: rename default rmodifier "nickserv" to "command_auth" (with new modifier "irc_command_auth"), add default rmodifier "message_auth" (modifier "irc_message_auth")
- script: add option script.scripts.autoload, add options "autoload", "noautoload" and "toggleautoload" for command `/script`, add action "A" (`Alt`+`a`) on script buffer (toggle autoload) ([task #12393](https://savannah.nongnu.org/task/?12393))
- xfer: add option xfer.file.auto_accept_nicks ([patch #7962](https://savannah.nongnu.org/patch/?7962))

### Bug fixes

- core: fix display of long lines without time (message beginning with two tabs)
- core: reset scroll in window before zooming on a merged buffer ([bug #38207](https://savannah.nongnu.org/bugs/?38207))
- core: fix refresh of item "completion": clear it after any action that is changing content of command line and after switch of buffer ([bug #38214](https://savannah.nongnu.org/bugs/?38214))
- core: fix structures before buffer data when a buffer is closed
- core: fix refresh of line after changes with hdata_update (update flag "displayed" according to filters)
- core: fix hidden lines for messages without date when option weechat.history.max_buffer_lines_minutes is set ([bug #38197](https://savannah.nongnu.org/bugs/?38197))
- core: use default hash/comparison callback for keys of type integer/pointer/time in hashtable
- api: do not display a warning by default when loading a script with a license different from GPL
- api: fix connection to servers with hook_connect on macOS ([bug #38496](https://savannah.nongnu.org/bugs/?38496))
- api: fix bug in function string_match when mask begins and ends with "*"
- api: allow hashtable with keys that are not strings in function hashtable_add_to_infolist
- api: fix function string_mask_to_regex: escape all special chars used in regex ([bug #38398](https://savannah.nongnu.org/bugs/?38398))
- guile: fix crash in function hdata_move
- guile: fix arguments given to callbacks (separate arguments instead of one list with arguments inside), Guile ≥ 2.0 is now required ([bug #38350](https://savannah.nongnu.org/bugs/?38350))
- guile: fix crash on calls to callbacks during load of script ([bug #38343](https://savannah.nongnu.org/bugs/?38343))
- irc: fix name of server buffer after `/server rename` (set name "server.name" instead of "name")
- irc: fix uncontrolled format string when sending unknown irc commands (if option irc.network.send_unknown_commands is on)
- irc: fix uncontrolled format string when sending ison command (for nicks monitored by `/notify`)
- irc: fix refresh of nick in input bar when joining a new channel with op status ([bug #38969](https://savannah.nongnu.org/bugs/?38969))
- irc: fix display of CTCP messages that contain bold attribute ([bug #38895](https://savannah.nongnu.org/bugs/?38895))
- irc: fix duplicate nick completion when someone rejoins the channel with same nick but a different case ([bug #38841](https://savannah.nongnu.org/bugs/?38841))
- irc: fix crash on command `/allchan /close`
- irc: fix default completion (like nicks) in commands `/msg`, `/notice`, `/query` and `/topic`
- irc: fix prefix color for nick when the prefix is not in irc.color.nick_prefixes: use default color (key "*")
- irc: fix display of malformed CTCP (without closing char) ([bug #38347](https://savannah.nongnu.org/bugs/?38347))
- irc: fix memory leak in purge of hashtables with joins (it was done only for the first server in the list)
- irc: add color in output of `/names` when result is on server buffer (channel not joined) ([bug #38070](https://savannah.nongnu.org/bugs/?38070))
- lua: remove use of functions for API constants
- lua: fix crash on stack overflow: call lua_pop for values returned by lua functions ([bug #38510](https://savannah.nongnu.org/bugs/?38510))
- perl: simplify code to load scripts
- python: fix crash when loading scripts with Python 3.x ([patch #8044](https://savannah.nongnu.org/patch/?8044))
- relay: fix uncontrolled format string in redirection of irc commands
- relay: rename compression "gzip" to "zlib" (compression is zlib, not gzip)
- relay: fix commands sync/desync in weechat protocol ([bug #38215](https://savannah.nongnu.org/bugs/?38215))
- ruby: fix crash in function hdata_move
- ruby: fix crash with Ruby 2.0: use one array for the last 6 arguments of function config_new_option ([bug #31050](https://savannah.nongnu.org/bugs/?31050))
- script: create "script" directory on each action, just in case it has been removed ([bug #38472](https://savannah.nongnu.org/bugs/?38472))
- scripts: create directories (language and language/autoload) on each action (install/remove/autoload), just in case they have been removed ([bug #38473](https://savannah.nongnu.org/bugs/?38473))
- scripts: do not allow empty script name in function register
- xfer: fix freeze of DCC file received: use non-blocking socket after connection to sender and ensure the ACK is properly sent ([bug #38340](https://savannah.nongnu.org/bugs/?38340))

### Build

- core: install icon file ([patch #7972](https://savannah.nongnu.org/patch/?7972))
- core: fix detection of iconv with CMake on macOS ([bug #38321](https://savannah.nongnu.org/bugs/?38321))
- guile: fix compilation with Guile 2.0
- python: fix detection of Python on Ubuntu Raring
- script: fix compilation on GNU/Hurd ([patch #7977](https://savannah.nongnu.org/patch/?7977))

## Version 0.4.0 (2013-01-20)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add buffer pointer in arguments for signals "input_search", "input_text_changed" and "input_text_cursor_moved"
- core: add option `diff` in command `/set` (list options with changed value)
- core: add color support in options weechat.look.prefix_{action|error|join|network|quit} ([task #9555](https://savannah.nongnu.org/task/?9555))
- core: display default values for changed config options in output of `/set`
- core: add command `/eval`, use expression in conditions for bars
- core: add option `-quit` in command `/upgrade` (save session and quit without restarting WeeChat, for delayed restoration)
- core: add incomplete mouse events "event-down" and "event-drag" ([task #11840](https://savannah.nongnu.org/task/?11840))
- api: allow return code WEECHAT_RC_OK_EAT in callbacks of hook_signal and hook_hsignal (stop sending the signal immediately)
- api: allow creation of structure with hdata_update (allowed for hdata "history")
- api: use hashtable "options" for command arguments in function hook_process_hashtable (optional, default is a split of string with command)
- api: add new function string_eval_expression
- api: connect with IPv6 by default in hook_connect (with fallback to IPv4), shuffle list of hosts for a same address, add argument "retry" for hook_connect, move "sock" from hook_connect arguments to callback of hook_connect ([task #11205](https://savannah.nongnu.org/task/?11205))
- aspell: add signal "aspell_suggest" (sent when new suggestions are displayed)
- aspell: add bar items "aspell_dict" (dictionary used on current buffer) and "aspell_suggest" (suggestions for misspelled word at cursor), add option aspell.check.suggestions ([task #12061](https://savannah.nongnu.org/task/?12061))
- irc: add tags "irc_nick1_xxx" and "irc_nick2_yyy" in message displayed for command "NICK"
- irc: return git version in CTCP VERSION and FINGER by default, add "$git" and "$versiongit" in format of CTCP replies
- irc: read local variable "autorejoin" in buffer to override server option "autorejoin" ([task #12256](https://savannah.nongnu.org/task/?12256))
- irc: add option `-auto` in command `/connect` ([task #9340](https://savannah.nongnu.org/task/?9340))
- irc: add support of "server-time" capability ([task #12255](https://savannah.nongnu.org/task/?12255))
- irc: add support of tags in messages
- irc: add command `/quiet`, fix display of messages 728/729 (quiet list, end of quiet list) ([task #12278](https://savannah.nongnu.org/task/?12278))
- irc: add option irc.network.alternate_nick to disable dynamic nick generation when all nicks are already in use on server ([task #12281](https://savannah.nongnu.org/task/?12281))
- irc: add option irc.network.whois_double_nick to double nick in command `/whois`
- irc: add option `-noswitch` in command `/join` ([task #12275](https://savannah.nongnu.org/task/?12275))
- perl: display script filename in error messages
- relay: add backlog and server capability "server-time" for irc protocol, add new options relay.irc.backlog_max_minutes, relay.irc.backlog_max_number, relay.irc.backlog_since_last_disconnect, relay.irc.backlog_tags, relay.irc.backlog_time_format ([task #12076](https://savannah.nongnu.org/task/?12076))
- relay: add support of IPv6, new option relay.network.ipv6, add support of "ipv4." and/or "ipv6." before protocol name, to force IPv4/IPv6 ([task #12270](https://savannah.nongnu.org/task/?12270))
- xfer: display remote IP address for DCC chat/file ([task #12289](https://savannah.nongnu.org/task/?12289))

### Bug fixes

- core: fix infinite loop when a regex gives an empty match ([bug #38112](https://savannah.nongnu.org/bugs/?38112))
- core: fix click in item "buffer_nicklist" when nicklist is a root bar ([bug #38080](https://savannah.nongnu.org/bugs/?38080))
- core: fix line returned when clicking on a bar (according to position and filling) ([bug #38069](https://savannah.nongnu.org/bugs/?38069))
- core: fix refresh of bars when applying layout ([bug #37944](https://savannah.nongnu.org/bugs/?37944), [bug #37952](https://savannah.nongnu.org/bugs/?37952))
- core: fix scroll to bottom of window (default key: `Alt`+`End`) when line displayed is bigger than chat area
- core: fix scroll in buffer after enabling/disabling some filters (if scroll is on a hidden line) ([bug #37885](https://savannah.nongnu.org/bugs/?37885))
- core: fix memory leak in case of error when building content of bar item for display
- core: fix detection of command in input: a single command char is considered as a command (API function string_input_for_buffer)
- core: search for a fallback template when a no template is matching command arguments
- core: fix refresh of windows after split (fix bug with horizontal separator between windows) ([bug #37874](https://savannah.nongnu.org/bugs/?37874))
- core: fix stuck mouse ([bug #36533](https://savannah.nongnu.org/bugs/?36533))
- core: fix default mouse buttons actions for script buffer (focus the window before executing action)
- core: fix scroll of one page down when weechat.look.scroll_page_percent is less than 100 ([bug #37875](https://savannah.nongnu.org/bugs/?37875))
- core: disable paste detection and confirmation if bar item "input_paste" is not used in a visible bar ([task #12327](https://savannah.nongnu.org/task/?12327))
- core: use high priority (50000) for commands `/command` and `/input` so that an alias will not take precedence over these commands ([bug #36353](https://savannah.nongnu.org/bugs/?36353))
- core: execute command with higher priority when many commands with same name are found with different priorities
- core: fix display of combining chars ([bug #37775](https://savannah.nongnu.org/bugs/?37775))
- core: fix display of zoomed/merged buffer (with number ≥ 2) after switching to it ([bug #37593](https://savannah.nongnu.org/bugs/?37593))
- core: fix display problem when option weechat.look.prefix_same_nick is set (problem with nick displayed in first line of screen) ([bug #37556](https://savannah.nongnu.org/bugs/?37556))
- core: fix wrapping of words with wide chars (the break was made before the correct position)
- api: do not call shell to execute command in hook_process (fix security problem when a plugin/script gives untrusted command) ([bug #37764](https://savannah.nongnu.org/bugs/?37764))
- alias: give higher priority to aliases (2000) so that they take precedence over an existing command
- aspell: ignore self and remote nicks in private buffers
- aspell: fix creation of spellers when number of dictionaries is different between two buffers
- guile: fix bad conversion of shared strings (replace calls to scm_i_string_chars by scm_to_locale_string) ([bug #38067](https://savannah.nongnu.org/bugs/?38067))
- irc: fix display of actions (`/me`) when they are received from a relay client (in channel and private buffers) ([bug #38027](https://savannah.nongnu.org/bugs/?38027))
- irc: fix memory leak when updating modes of channel
- irc: fix crash on `/upgrade` (free channels before server data when a server is destroyed) ([bug #37736](https://savannah.nongnu.org/bugs/?37736))
- irc: fix crash when decoding IRC colors in strings ([bug #37704](https://savannah.nongnu.org/bugs/?37704))
- irc: fix refresh of bar item "away" after command `/away` or `/disconnect`
- irc: send whois on self nick when `/whois` is done without argument on a channel ([task #12273](https://savannah.nongnu.org/task/?12273))
- irc: remove local variable "away" in server/channels buffers after server disconnection ([bug #37582](https://savannah.nongnu.org/bugs/?37582))
- irc: fix crash when message 352 has too few arguments ([bug #37513](https://savannah.nongnu.org/bugs/?37513))
- irc: remove unneeded server disconnect when server buffer is closed and server is already disconnected
- perl: fix calls to callbacks during load of script when multiplicity is disabled ([bug #38044](https://savannah.nongnu.org/bugs/?38044))
- relay: fix duplicated messages sent to irc clients (when messages are redirected) ([bug #37870](https://savannah.nongnu.org/bugs/?37870))
- relay: fix memory leak when adding hdata to a message (weechat protocol)
- relay: fix crash after `/upgrade` when a client is connected
- relay: add missing "ssl." in output of `/relay listrelay`
- script: fix scroll with mouse when window with script buffer is not the current window (do not force a switch to script buffer in current window)
- xfer: fix memory leak when refreshing xfer buffer
- xfer: add missing tags in DCC chat messages: nick_xxx, prefix_nick_ccc, logN
- xfer: limit bytes received to file size (for DCC file received), fix crash when displaying a xfer file with pos greater than size

### Build

- core: add git version in build, display it in `weechat-curses --help` and `/version`
- core: stop CMake if gcrypt lib is not found ([bug #37671](https://savannah.nongnu.org/bugs/?37671))
- guile: fix detection of Guile in configure
- script: fix compilation on macOS

## Version 0.3.9.2 (2012-11-18)

### Bug fixes

- core: do not call shell to execute command in hook_process (fix security problem when a plugin/script gives untrusted command) ([bug #37764](https://savannah.nongnu.org/bugs/?37764), [CVE-2012-5534](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-5534))

## Version 0.3.9.1 (2012-11-09)

### Bug fixes

- irc: fix crash when decoding IRC colors in strings ([bug #37704](https://savannah.nongnu.org/bugs/?37704), [CVE-2012-5854](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-5854))

## Version 0.3.9 (2012-09-29)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add signals for plugins loaded/unloaded
- core: add default key `Alt`+`x` (zoom on merged buffer) ([task #11029](https://savannah.nongnu.org/task/?11029))
- core: add mouse bindings `Ctrl` + wheel up/down to scroll horizontally buffers with free content
- core: add option weechat.startup.sys_rlimit to set system resource limits for WeeChat process
- core: add option `swap` in command `/buffer` ([task #11373](https://savannah.nongnu.org/task/?11373))
- core: add hdata "hotlist"
- core: add support of arrays in hdata variables
- core: add command line option `-r` (or `--run-command`) to run command(s) after startup of WeeChat
- core: add function hook_set in plugin API, add "subplugin" in hooks (set by script plugins), display subplugin in `/help` on commands ([task #12049](https://savannah.nongnu.org/task/?12049))
- core: add option weechat.look.jump_smart_back_to_buffer (jump back to initial buffer after reaching end of hotlist, on by default, which is old behavior)
- core: add default key `Alt`+`s` (toggle aspell)
- core: add callback "nickcmp" in buffers
- core: add horizontal separator between windows, new options weechat.look.window_separator_{horizontal|vertical}
- core: add options weechat.look.color_nick_offline and weechat.color.chat_nick_offline{_highlight|_highlight_bg} to use different color for offline nicks in prefix ([task #11109](https://savannah.nongnu.org/task/?11109))
- api: allow update for some variables of hdata, add new functions hdata_update and hdata_set
- api: add info "locale" for info_get (locale used to translate messages)
- api: add new function util_version_number
- aspell: add option aspell.check.enabled, add options enable/disable/toggle for command `/aspell` (rename options enable/disable/dictlist to setdict/deldict/listdict), display aspell status with `/aspell` ([task #11988](https://savannah.nongnu.org/task/?11988))
- irc: generate alternate nicks dynamically when all nicks are already in use ([task #12209](https://savannah.nongnu.org/task/?12209))
- irc: add bar item "buffer_modes", remove option irc.look.item_channel_modes ([task #12022](https://savannah.nongnu.org/task/?12022))
- irc: add option irc.look.ctcp_time_format to customize reply to CTCP TIME ([task #12150](https://savannah.nongnu.org/task/?12150))
- irc: move options from core to irc plugin: weechat.look.nickmode to irc.look.nick_mode (new type: integer with values: none/prefix/action/both) and weechat.look.nickmode_empty to irc.look.nick_mode_empty
- logger: add tags in backlog lines displayed when opening buffer
- logger: add messages "Day changed to" in backlog ([task #12187](https://savannah.nongnu.org/task/?12187))
- relay: add support of SSL (for irc and weechat protocols), new option relay.network.ssl_cert_key ([task #12044](https://savannah.nongnu.org/task/?12044))
- relay: add option relay.color.client
- relay: add object type "arr" (array) in WeeChat protocol
- script: new plugin "script" (script manager, replacing scripts weeget.py and script.pl)
- scripts: add signals for scripts loaded/unloaded/installed/removed
- scripts: add hdata with list of scripts for each language

### Bug fixes

- core: fix display bug when end of a line is displayed on top of chat (last line truncated and MORE(0) in status bar) ([bug #37203](https://savannah.nongnu.org/bugs/?37203))
- core: fix IP address returned by hook_connect (return IP really used, not first IP for hostname)
- core: display spaces at the end of messages in chat area ([bug #37024](https://savannah.nongnu.org/bugs/?37024))
- core: fix infinite loop in display when chat area has width of 1 with a bar displayed on the right (nicklist by default) ([bug #37089](https://savannah.nongnu.org/bugs/?37089))
- core: fix display of "bar more down" char when text is truncated by size_max in bars with vertical filling ([bug #37054](https://savannah.nongnu.org/bugs/?37054))
- core: fix color of long lines (displayed on more than one line on screen) under FreeBSD ([bug #36999](https://savannah.nongnu.org/bugs/?36999))
- core: return error string to callback of hook_connect if getaddrinfo fails in child process
- core: scroll to bottom of window after reaching first or last highlight with keys `Alt`+`p` / `Alt`+`n`
- core: fix refresh of bar items when switching window
- core: fix refresh of bar items "buffer_filter" and "scroll" in root bars ([bug #36816](https://savannah.nongnu.org/bugs/?36816))
- core: allow again names beginning with "#" for bars, proxies and filters
- core: escape special chars (`#[\`) in configuration files for name of options ([bug #36584](https://savannah.nongnu.org/bugs/?36584))
- aspell: add missing dictionaries (ast/grc/hus/kn/ky)
- charset: do not allow "UTF-8" in charset decoding options (useless because UTF-8 is the internal WeeChat charset)
- fifo: ignore read failing with error EAGAIN ([bug #37019](https://savannah.nongnu.org/bugs/?37019))
- guile: fix crash when unloading a script without pointer to interpreter
- irc: fix rejoin of channels with a key, ignore value "*" sent by server for key ([bug #24131](https://savannah.nongnu.org/bugs/?24131))
- irc: fix SASL mechanism "external" ([bug #37274](https://savannah.nongnu.org/bugs/?37274))
- irc: fix parsing of message 346 when no nick/time are given ([bug #37266](https://savannah.nongnu.org/bugs/?37266))
- irc: switch to next address after a timeout when connecting to server ([bug #37216](https://savannah.nongnu.org/bugs/?37216))
- irc: fix bug when changing server option "addresses" with less addresses ([bug #37215](https://savannah.nongnu.org/bugs/?37215))
- irc: add network prefix in irc (dis)connection messages
- irc: fix split of received IRC message: keep spaces at the end of message
- irc: fix bug with prefix chars which are in chanmodes with a type different from "B" ([bug #36996](https://savannah.nongnu.org/bugs/?36996))
- irc: fix format of message "USER" (according to RFC 2812) ([bug #36825](https://savannah.nongnu.org/bugs/?36825))
- irc: fix parsing of user modes (ignore everything after first space) ([bug #36756](https://savannah.nongnu.org/bugs/?36756), [bug #31572](https://savannah.nongnu.org/bugs/?31572))
- irc: fix freeze when reading on socket with SSL enabled (use non-blocking sockets) ([bug #35097](https://savannah.nongnu.org/bugs/?35097))
- irc: allow again names beginning with "#" for servers
- lua: fix crash when unloading a script without pointer to interpreter
- python: fix crash when unloading a script without pointer to interpreter
- relay: fix freeze when writing on relay socket (use non-blocking sockets in relay for irc and weechat protocols) ([bug #36655](https://savannah.nongnu.org/bugs/?36655))
- scripts: fix deletion of configuration files when script is unloaded ([bug #36977](https://savannah.nongnu.org/bugs/?36977))
- scripts: fix function unhook_all: delete only callbacks of hooks and add missing call to unhook
- scripts: ignore call to register (with a warning) if script is already registered
- xfer: fix DCC transfer error ([bug #37432](https://savannah.nongnu.org/bugs/?37432))

### Documentation

- add Japanese user's guide ([patch #7827](https://savannah.nongnu.org/patch/?7827)), scripting guide and tester's guide

### Build

- core: move the set of CMake policy CMP0003 in directory src (so it applies to all plugins) ([bug #37311](https://savannah.nongnu.org/bugs/?37311))
- core: fix names of cache variables in configure.in ([bug #36971](https://savannah.nongnu.org/bugs/?36971))
- core: add CMake option "MANDIR" ([bug #36776](https://savannah.nongnu.org/bugs/?36776))
- guile: fix path of Guile include dirs in CMake build ([patch #7790](https://savannah.nongnu.org/patch/?7790))
- lua: add support of Lua 5.2
- python: fix detection of Python (first try "python2.x" and then "python") ([bug #36835](https://savannah.nongnu.org/bugs/?36835))
- ruby: add detection of Ruby 1.9.3

## Version 0.3.8 (2012-06-03)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add option weechat.look.prefix_same_nick (hide or change prefix on messages whose nick is the same as previous message) ([task #11965](https://savannah.nongnu.org/task/?11965))
- core: convert tabs to spaces in text pasted ([bug #25028](https://savannah.nongnu.org/bugs/?25028))
- core: add a connection timeout for child process in hook_connect ([bug #35966](https://savannah.nongnu.org/bugs/?35966))
- core: add support of terminal "bracketed paste mode", new options weechat.look.paste_bracketed and weechat.look.paste_bracketed_timer_delay ([task #11316](https://savannah.nongnu.org/task/?11316))
- core: support lines of 16 Kb long in configuration files (instead of 1 Kb)
- core: convert options weechat.look.prefix_align_more and weechat.look.prefix_buffer_align_more from boolean to string ([task #11197](https://savannah.nongnu.org/task/?11197))
- core: follow symbolic links when writing configuration files (.conf) ([task #11779](https://savannah.nongnu.org/task/?11779))
- api: add list "gui_buffer_last_displayed" in hdata "buffer"
- irc: add option `fakerecv` in command `/server` to simulate a received IRC message (not documented, for debug only)
- irc: add option `-pending` in command `/disconnect` (cancel auto-reconnection on servers currently reconnecting) ([task #11985](https://savannah.nongnu.org/task/?11985))
- irc: add signals and tags in messages for irc notify ([task #11887](https://savannah.nongnu.org/task/?11887))
- irc: add support of "external" SASL mechanism ([task #11864](https://savannah.nongnu.org/task/?11864))
- irc: allow more than one nick in command `/invite`
- logger: add colors for backlog lines and end of backlog, new options: logger.color.backlog_line and logger.color.backlog_end ([task #11966](https://savannah.nongnu.org/task/?11966))
- relay: add signals "upgrade" and "upgrade_ended" in WeeChat protocol
- relay: add "date_printed" and "highlight" in signal "_buffer_line_added" (WeeChat protocol)
- rmodifier: add default rmodifier "quote_pass" to hide password in command `/quote pass` ([bug #36250](https://savannah.nongnu.org/bugs/?36250))
- rmodifier: add default rmodifier "server" to hide passwords in commands `/server` and `/connect` ([task #11993](https://savannah.nongnu.org/task/?11993))
- rmodifier: add option "release" in default rmodifier "nickserv" (used to hide passwords in command `/msg nickserv`) ([bug #35705](https://savannah.nongnu.org/bugs/?35705))

### Bug fixes

- core: fix crash in focus hook for nicklist ([bug #36271](https://savannah.nongnu.org/bugs/?36271))
- core: fix truncated configuration files (zero-length) after system crash ([bug #36383](https://savannah.nongnu.org/bugs/?36383))
- core: fix display bugs and crashes with small windows ([bug #36107](https://savannah.nongnu.org/bugs/?36107))
- core: fix display bug with prefix when length is greater than max and prefix is ending with a wide char ([bug #36032](https://savannah.nongnu.org/bugs/?36032))
- core: fix lost scroll when switching to a buffer with a pending search
- core: fix display of wide chars on last column of chat area ([patch #7733](https://savannah.nongnu.org/patch/?7733))
- api: display warning in scripts when invalid pointers (malformed strings) are given to plugin API functions (warning displayed if debug for plugin is ≥ 1)
- scripts: fix type of argument "rc" in callback of hook_process (from string to integer)
- guile: fix crash on ARM when loading guile plugin ([bug #36479](https://savannah.nongnu.org/bugs/?36479))
- guile: add missing function hook_process_hashtable in API
- irc: update channel modes by using chanmodes from message 005 (do not send extra command "MODE" to server), fix parsing of modes ([bug #36215](https://savannah.nongnu.org/bugs/?36215))
- irc: hide everything after "identify" or "register" in messages to nickserv when option irc.look.hide_nickserv_pwd is on ([bug #36362](https://savannah.nongnu.org/bugs/?36362))
- irc: set user modes only if target nick is self nick in message 221 ([patch #7754](https://savannah.nongnu.org/patch/?7754))
- irc: force the clear of nicklist when joining a channel (nicklist was not sync after znc reconnection) ([bug #36008](https://savannah.nongnu.org/bugs/?36008))
- irc: do not send command "MODE #channel" on manual `/names` (do it only when names are received on join of channel) ([bug #35930](https://savannah.nongnu.org/bugs/?35930))
- irc: do not allow the creation of two servers with same name but different case (fix error when writing file irc.conf) ([bug #35840](https://savannah.nongnu.org/bugs/?35840))
- irc: update away flag for nicks on manual `/who`
- irc: display privmsg messages to "@#channel" and "+#channel" in channel buffer ([bug #35331](https://savannah.nongnu.org/bugs/?35331))
- irc: fix redirection of message when message is queued for sending on server
- irc: check notify immediately when adding a nick to notify list, improve first notify message for a nick ([bug #35731](https://savannah.nongnu.org/bugs/?35731))
- irc: fix display of color in hostname (join/part/quit messages)
- irc: compute hash to find nick color for nick in server message when nick is not in nicklist
- irc: close server buffer when server is deleted
- irc: add search for lower case nicks in option irc.look.nick_color_force
- logger: fix charset of lines displayed in backlog when terminal charset is different from UTF-8 ([bug #36379](https://savannah.nongnu.org/bugs/?36379))
- perl: fix crash on quit on macOS
- relay: keep spaces in beginning of "input" received from client (WeeChat protocol)
- relay: fix crash on `/upgrade` when client is connected using WeeChat protocol
- relay: redirect some irc messages from clients to hide output (messages: mode, ison, list, names, topic, who, whois, whowas, time, userhost) ([bug #33516](https://savannah.nongnu.org/bugs/?33516))
- tcl: add missing function hdata_char in API
- tcl: fix pointer sent to function hook_signal_send when type of data is a pointer

### Documentation

- add Japanese FAQ ([patch #7781](https://savannah.nongnu.org/patch/?7781))

### Build

- perl: fix compilation on macOS ([bug #30701](https://savannah.nongnu.org/bugs/?30701))

## Version 0.3.7 (2012-02-26)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add support of flags in regular expressions and highlight options
- core: add type "hashtable" for hdata
- core: add signals "buffer_line_added" and "window_switch"
- core: add default keys `Ctrl`+`Left` / `Ctrl`+`Right` (`meta2-1;5D` / `meta2-1;5C`) for gnome-terminal
- core: add option `hooks` in command `/debug`
- core: add option weechat.look.scroll_bottom_after_switch (if enabled, restore old behavior before fix of [bug #25555](https://savannah.nongnu.org/bugs/?25555) in version 0.3.5)
- core: add new option weechat.completion.base_word_until_cursor: allow completion in middle of words (enabled by default) ([task #9771](https://savannah.nongnu.org/task/?9771))
- core: add option `jump_last_buffer_displayed` in command `/input` (key: `Alt`+`/`) ([task #11553](https://savannah.nongnu.org/task/?11553))
- core: add option weechat.history.max_buffer_lines_minutes: maximum number of minutes in history per buffer ([task #10900](https://savannah.nongnu.org/task/?10900)), rename option weechat.history.max_lines to weechat.history.max_buffer_lines_number
- core: add optional arguments for command `/plugin load/reload/autoload`
- core: use extended regex in filters ([task #9497](https://savannah.nongnu.org/task/?9497), [patch #7616](https://savannah.nongnu.org/patch/?7616))
- api: add modifier "input_text_for_buffer" ([bug #35317](https://savannah.nongnu.org/bugs/?35317))
- api: add support of URL in hook_process / hook_process_hashtable ([task #10247](https://savannah.nongnu.org/task/?10247))
- api: add new functions strcasecmp_range, strncasecmp_range, string_regex_flags, string_regcomp, hashtable_map_string, hook_process_hashtable, hdata_check_pointer, hdata_char, hdata_hashtable and nicklist_get_next_item
- alias: add default alias `/umode` to `/mode $nick`
- irc: add option "capabilities" in servers to enable client capabilities on connection
- irc: add signal "irc_server_opened"
- irc: add signal "xxx,irc_out1_yyy" and modifier "irc_out1_xxx" (outgoing message before automatic split to fit in 512 bytes)
- irc: add alias "ctcp" for target buffer of CTCP messages
- irc: add options irc.look.highlight_{server|channel|pv} to customize or disable default nick highlight ([task #11128](https://savannah.nongnu.org/task/?11128))
- irc: use redirection to get channel modes after update of modes on channel, display output of `/mode #channel`, allow `/mode` without argument (display modes of current channel or user modes on server buffer)
- irc: add optional server in info "irc_is_channel" (before channel name) ([bug #35124](https://savannah.nongnu.org/bugs/?35124)), add optional server in info_hashtable "irc_message_parse"
- irc: add case-insensitive string comparison based on casemapping of server (rfc1459, strict-rfc1459, ascii) ([bug #34239](https://savannah.nongnu.org/bugs/?34239))
- irc: add option irc.color.mirc_remap to remap mirc colors in messages to WeeChat colors
- irc: allow URL "irc://" in command `/connect`
- irc: use extended regex in commands `/ignore` and `/list`
- guile: new script plugin for scheme ([task #7289](https://savannah.nongnu.org/task/?7289))
- python: add support of Python 3.x ([task #11704](https://savannah.nongnu.org/task/?11704))
- relay: add WeeChat protocol for remote GUI
- xfer: display origin of xfer in core and xfer buffers ([task #10956](https://savannah.nongnu.org/task/?10956))

### Internationalization

- add Japanese translations

### Bug fixes

- core: fix expand of path `~` to home of user in function string_expand_home (`~/xxx` was OK, but not `~`)
- core: fix memory leak when closing buffer
- core: fix memory leak in function util_search_full_lib_name
- core: automatically add newline char after last pasted line (when pasting many lines with confirmation) ([task #10703](https://savannah.nongnu.org/task/?10703))
- core: fix bug with layout: assign layout number in buffers when doing `/layout save`
- core: do not auto add space after nick completer if option weechat.completion.nick_add_space is off
- core: fix signal "buffer_switch": send it only once when switching buffer ([bug #31158](https://savannah.nongnu.org/bugs/?31158))
- core: move option `scroll_unread` from command `/input` to `/window`
- core: save current mouse state in option weechat.look.mouse (set option when mouse state is changed with command `/mouse`)
- core: apply filters after full reload of configuration files (with `/reload`) ([bug #31182](https://savannah.nongnu.org/bugs/?31182))
- core: allow list for option weechat.plugin.extension (makes weechat.conf portable across Un*x and Windows) ([task #11479](https://savannah.nongnu.org/task/?11479))
- core: display error in command `/buffer` if arguments are wrong ([bug #34180](https://savannah.nongnu.org/bugs/?34180))
- core: fix help on plugin option when config_set_desc_plugin is called to set help on newly created option
- core: enable background process under Cygwin to connect to servers, fix reconnection problem ([bug #34626](https://savannah.nongnu.org/bugs/?34626))
- aspell: fix URL detection (do not check spelling of URLs) ([bug #34040](https://savannah.nongnu.org/bugs/?34040))
- irc: fix memory leak in SASL DH-BLOWFISH authentication
- irc: fix memory leak when a server is deleted
- irc: fix self-highlight when using `/me` with an IRC bouncer like znc ([bug #35123](https://savannah.nongnu.org/bugs/?35123))
- irc: use low priority for MODE sent automatically by WeeChat (when joining channel)
- irc: do not use option irc.look.nick_color_stop_chars for forced nick colors ([bug #33480](https://savannah.nongnu.org/bugs/?33480))
- irc: reset read marker of current buffer on manual `/join`
- irc: fix crash when signon time in message 317 (whois, idle) is invalid (too large) ([bug #34905](https://savannah.nongnu.org/bugs/?34905))
- irc: do not delete servers added in irc.conf on `/reload` ([bug #34872](https://savannah.nongnu.org/bugs/?34872))
- irc: remove autorejoin on channels when disconnected from server ([bug #32207](https://savannah.nongnu.org/bugs/?32207))
- irc: display messages kick/kill/mode/topic even if nick is ignored ([bug #34853](https://savannah.nongnu.org/bugs/?34853))
- irc: display channel voice notices received in channel buffer ([bug #34762](https://savannah.nongnu.org/bugs/?34762)), display channel/op notices sent in channel buffer
- irc: auto-connect to servers created with "irc://" on command line but not other servers if `-a` (`--no-connect`) is given
- perl: increment count of hash returned by API (fix crash when script tries to read hash without making a copy)
- relay: do not create relay if there is a problem with socket creation ([bug #35345](https://savannah.nongnu.org/bugs/?35345))
- ruby: fix crash when reloading ruby plugin ([bug #34474](https://savannah.nongnu.org/bugs/?34474))

### Documentation

- add developer's guide ([task #5416](https://savannah.nongnu.org/task/?5416))

### Build

- core: add library "pthread" in CMake file for link on OpenBSD
- core: add WEECHAT_HOME option in CMake and configure to setup default WeeChat home (default is "~/.weechat") ([task #11266](https://savannah.nongnu.org/task/?11266))
- core: fix compilation under OpenBSD 5.0 (lib utf8 not needed anymore) ([bug #34727](https://savannah.nongnu.org/bugs/?34727))
- core: fix compilation error with "pid_t" on macOS ([bug #34639](https://savannah.nongnu.org/bugs/?34639))

## Version 0.3.6 (2011-10-22)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add color attribute "|" (keep attributes) and value "resetcolor" for function color in plugin API (used by irc plugin to keep bold/reverse/underlined in message when changing color) ([bug #34550](https://savannah.nongnu.org/bugs/?34550))
- core: add new option weechat.look.color_basic_force_bold, off by default: bold is used only if terminal has less than 16 colors ([patch #7621](https://savannah.nongnu.org/patch/?7621))
- core: add default key `F5` (`meta2-[E`) for Linux console
- core: add "inactive" colors for inactive windows and lines in merged buffers, new options: weechat.look.color_inactive_window, weechat.look.color_inactive_buffer, weechat.look.color_inactive_message, weechat.look.color_inactive_prefix, weechat.look.color_inactive_prefix_buffer, weechat.look.color_inactive_time, weechat.color.chat_inactive_line, weechat.color.chat_inactive_window, weechat.color.chat_prefix_buffer_inactive_line
- core: do automatic zoom on current window when terminal becomes too small for windows
- core: add new options weechat.look.bar_more_left/right/up/down
- core: add new option weechat.look.item_buffer_filter
- core: allow name of buffer for command `/buffer clear` ([task #11269](https://savannah.nongnu.org/task/?11269))
- core: add new command `/repeat` (execute a command several times)
- core: save and restore layout for buffers and windows on `/upgrade`
- core: add option `-all` in command `/buffer unmerge`
- core: add number in windows (add optional argument `-window` so some actions for command `/window`)
- core: allow buffer name in `/buffer close`
- core: add support of mouse: new command `/mouse`, new key context "mouse", new options weechat.look.mouse and weechat.look.mouse_timer_delay ([task #5435](https://savannah.nongnu.org/task/?5435))
- core: add command `/cursor` (free movement of cursor on screen), with key context "cursor"
- core: automatic scroll direction in `/bar scroll` (x/y is now optional)
- core: add optional delay for key grab (commands `/input grab_key` and `/input grab_key_command`, default is 500 milliseconds)
- core: allow plugin name in command `/buffer name`
- core: add context "search" for keys (to define keys used during search in buffer with `Ctrl`+`r`)
- core: add new option weechat.look.separator_vertical, rename option weechat.look.hline_char to weechat.look.separator_horizontal
- core: add local variable "highlight_regex" in buffers
- core: add "hdata" (direct access to WeeChat/plugin data)
- core: add option weechat.look.eat_newline_glitch (do not add new line at end of each line displayed)
- core: add options `infolists`, `hdata` and `tags` for command `/debug`
- core: add horizontal scrolling for buffers with free content (command `/window scroll_horiz`) ([task #11112](https://savannah.nongnu.org/task/?11112))
- core: change default value of option weechat.network.gnutls_ca_file to "/etc/ssl/certs/ca-certificates.crt"
- api: add info "cursor_mode"
- api: add new functions key_bind, key_unbind, hook_focus, hdata_new, hdata_new_var, hdata_new_list, hdata_get, hdata_get_var_offset, hdata_get_var_type, hdata_get_var_type_string, hdata_get_var_hdata, hdata_get_var, hdata_get_var_at_offset, hdata_get_list, hdata_move, hdata_integer, hdata_string, hdata_pointer, hdata_time, hdata_get_string
- irc: allow reason for command `/disconnect`
- irc: allow server name for commands `/die` and `/restart`
- irc: add new info_hashtable "irc_message_split"
- irc: add prefix "#" for all channels on join (if no prefix given)
- irc: improve split of privmsg message (keep ctcp), add split of ison, join, notice, wallops, 005, 353 ([bug #29879](https://savannah.nongnu.org/bugs/?29879), [bug #33448](https://savannah.nongnu.org/bugs/?33448), [bug #33592](https://savannah.nongnu.org/bugs/?33592))
- logger: add option logger.file.flush_delay ([task #11118](https://savannah.nongnu.org/task/?11118))

### Bug fixes

- core: fix freeze when calling function util_file_get_content with a directory instead of a filename
- core: display timeout for hook_process command only if debug for core is enabled ([task #11401](https://savannah.nongnu.org/task/?11401))
- core: bufferize lines displayed before core buffer is created, to display them in buffer when it is created
- core: fix display of background color in chat area after line feed
- core: fix paste detection (problem with end of lines)
- core: fix display of paste multi-line prompt with a root input bar ([bug #34305](https://savannah.nongnu.org/bugs/?34305))
- core: replace deprecated GnuTLS function gnutls_certificate_client_set_retrieve_function by new function gnutls_certificate_set_retrieve_function (GnuTLS ≥ 2.11.0)
- core: use dynamic buffer size for calls to vsnprintf
- core: fix memory leak in unhook of hook_connect
- core: fix memory leak in display of empty bar items
- core: fix input of wide UTF-8 chars under Cygwin ([bug #34061](https://savannah.nongnu.org/bugs/?34061))
- core: fix bugs with automatic layout ([bug #26110](https://savannah.nongnu.org/bugs/?26110)), add support of merged buffers in layout ([task #10893](https://savannah.nongnu.org/task/?10893))
- core: fix crash when invalid UTF-8 chars are inserted in command line ([bug #33471](https://savannah.nongnu.org/bugs/?33471))
- core: stop horizontal bar scroll at the end of content (for bars with horizontal filling) ([bug #27908](https://savannah.nongnu.org/bugs/?27908))
- core: fix crash when building hashtable string with keys and values
- core: replace buffer name by window number in `/bar scroll`
- core: fix bugs with key "^" ([bug #32072](https://savannah.nongnu.org/bugs/?32072), [bug #21381](https://savannah.nongnu.org/bugs/?21381))
- core: fix bugs with bar windows: do not create bar windows for hidden bars
- core: fix completion bug when two words for completion are equal but with different case
- core: fix completion for command arguments when same command exists in many plugins ([bug #33753](https://savannah.nongnu.org/bugs/?33753))
- core: fix freeze when hook_fd is called with a bad file/socket ([bug #33619](https://savannah.nongnu.org/bugs/?33619))
- core: fix bug with option weechat.look.hotlist_count_max (value+1 was used)
- api: use arguments for infolist "window" to return only one window by number
- api: fix bug with function config_set_desc_plugin (use immediately description for option when function is called)
- scripts: fix crash with scripts not auto-loaded having a buffer opened after `/upgrade` (input/close callbacks for buffer not set properly)
- irc: fix display of items "away" and "lag" in root bars, refresh all irc bar items on signal "buffer_switch" ([bug #34466](https://savannah.nongnu.org/bugs/?34466))
- irc: fix crash on malformed irc notice received (without message after target)
- irc: add missing messages for whois: 223, 264, 343
- irc: use high priority queue for sending modes and wallchops messages
- irc: rename info_hashtable "irc_parse_message" to "irc_message_parse"
- irc: use color "default" for any invalid color in option weechat.color.chat_nick_colors
- irc: send WHO command to check away nicks only if channel was not parted
- irc: fix crash when malformed IRC message 352 (WHO) is received ([bug #33790](https://savannah.nongnu.org/bugs/?33790))
- irc: fix crash when command `/buffer close` is used in a server command to close server buffer during connection ([bug #33763](https://savannah.nongnu.org/bugs/?33763))
- irc: fix crash when `/join` command is executed on a non-irc buffer ([bug #33742](https://savannah.nongnu.org/bugs/?33742))
- irc: fix bug with comma in irc color code: do not strip comma if it is not followed by a digit ([bug #33662](https://savannah.nongnu.org/bugs/?33662))
- irc: switch to buffer on `/join #channel` if channel buffer already exists
- irc: set host for nick on each channel message and nick change (if not already set)
- irc: update host of nicks on manual `/who`
- irc: fix memory leak on plugin unload (free ignores)
- irc: fix memory leak in message parser (when called from other plugins like relay) ([bug #33387](https://savannah.nongnu.org/bugs/?33387))
- relay: fix bug with self nick when someone changes its nick on channel ([bug #33739](https://savannah.nongnu.org/bugs/?33739))
- relay: fix memory leak (free some parsed messages) ([bug #33387](https://savannah.nongnu.org/bugs/?33387))
- relay: fix memory leak on plugin load (free raw messages)
- perl: replace calls to SvPV by SvPV_nolen ([patch #7436](https://savannah.nongnu.org/patch/?7436))

### Build

- core: fix compilation error (INSTALLPREFIX undeclared) on macOS and when compiling with included gettext ([bug #26690](https://savannah.nongnu.org/bugs/?26690))

## Version 0.3.5 (2011-05-15)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add buffer to hotlist if away is set on buffer (even if buffer is displayed), new option weechat.look.hotlist_add_buffer_if_away ([task #10948](https://savannah.nongnu.org/task/?10948))
- core: add option `balance` in command `/window` (key: `Alt`+`w`, `Alt`+`b`)
- core: add option `swap` in command `/window` (key: `Alt`+`w`, `Alt`+`s`) ([task #11001](https://savannah.nongnu.org/task/?11001))
- core: add option weechat.look.hotlist_buffer_separator
- core: add messages counts in hotlist for each buffer, new options: weechat.look.hotlist_count_max, weechat.look.hotlist_count_min_msg and weechat.color.status_count_{msg|private|highlight|other}
- core: add tag "notify_none" (line with this tag will not update hotlist)
- core: add optional bar name in command `/bar default`
- core: add new option weechat.look.highlight_tags (force highlight on tags)
- core: allow list of buffers in command `/filter` (exclusion with prefix "!") ([task #10880](https://savannah.nongnu.org/task/?10880))
- core: allow relative size for command `/window resize`
- core: add some default keys for gnome-terminal (`Home` / `End`, `Ctrl`+`Up` / `Ctrl`+`Down`, `Alt`+`PgUp` / `Alt`+`PgDn`)
- core: add option `memory` in command `/debug`
- core: add option weechat.look.read_marker_string
- core: add some chars after cursor when scrolling input line: new option weechat.look.input_cursor_scroll ([bug #21391](https://savannah.nongnu.org/bugs/?21391))
- core: add color "gray"
- core: add attributes for colors ("*": bold, "!": reverse, "_": underline)
- core: dynamically allocate color pairs (extended colors can be used without being added with command `/color`), auto reset of color pairs with option weechat.look.color_pairs_auto_reset
- core: allow background for nick colors (using ":")
- core: remember scroll position for all buffers in windows ([bug #25555](https://savannah.nongnu.org/bugs/?25555))
- core: improve display of commands lists in `/help` (add arguments -list and -listfull) ([task #10299](https://savannah.nongnu.org/task/?10299))
- core: improve arguments displayed in `/help` of commands
- api: add new function config_set_desc_plugin ([task #10925](https://savannah.nongnu.org/task/?10925))
- api: add new functions buffer_match_list and window_search_with_buffer
- aspell: add section "option" in aspell.conf for speller options ([task #11083](https://savannah.nongnu.org/task/?11083))
- irc: add new options irc.color.topic_old and irc.color.topic_new
- irc: add option "ssl_priorities" in servers ([task #10106](https://savannah.nongnu.org/task/?10106), [debian #624055](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=624055))
- irc: add modifier "irc_in2_xxx" (called after charset decoding)
- irc: add new options irc.look.buffer_switch_autojoin and irc.look.buffer_switch_join ([task #8542](https://savannah.nongnu.org/task/?8542), [task #10506](https://savannah.nongnu.org/task/?10506))
- irc: add new option irc.look.smart_filter_nick
- irc: add new options irc.look.color_nicks_in_nicklist and irc.look.color_nicks_in_names
- irc: replace options irc.color.nick_prefix_{op|halfop|voice|user} by a single option irc.color.nick_prefixes ([task #10888](https://savannah.nongnu.org/task/?10888))

### Bug fixes

- core: fix scroll in windows with `/window scroll` (skip lines "Day changed to")
- core: recalculate buffer_max_length when buffer short name is changed ([patch #7441](https://savannah.nongnu.org/patch/?7441))
- core: do not update hotlist during upgrade
- core: apply new value of option weechat.look.buffer_notify_default to all opened buffers
- core: prohibit names beginning with "#" for bars, proxies, filters and IRC servers ([bug #33020](https://savannah.nongnu.org/bugs/?33020))
- core: create default bars only if no bar is defined in configuration file
- core: fix bug with repeat of last completion ("%*"), which failed when many templates are used in completion
- core: reload file with certificate authorities when option weechat.network.gnutls_ca_file is changed
- core: rebuild bar content when items are changed in an hidden bar
- core: fix verification of SSL certificates by calling GnuTLS verify callback ([patch #7459](https://savannah.nongnu.org/patch/?7459), [CVE-2011-1428](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2011-1428))
- core: fix crash when using column filling in bars with some empty items ([bug #32565](https://savannah.nongnu.org/bugs/?32565))
- core: fix terminal title when $TERM starts with "screen"
- plugins: fix memory leaks when setting buffer callbacks after `/upgrade` (plugins: irc, relay, xfer, scripts)
- aspell: fix spellers used after switch of window ([bug #32811](https://savannah.nongnu.org/bugs/?32811))
- irc: fix parsing of message 332 when no topic neither colon are found (bug with bip proxy)
- irc: fix nick color in private when option irc.look.nick_color_force is changed
- irc: fix tags for messages sent with `/msg` command ([bug #33169](https://savannah.nongnu.org/bugs/?33169))
- irc: fix memory leak when copying or renaming server
- irc: do not rejoin channels where `/part` has been issued before reconnection to server ([bug #33029](https://savannah.nongnu.org/bugs/?33029))
- irc: use nick color for users outside the channel
- irc: update short name of server buffer when server is renamed
- irc: fix local variable "away" on server buffer (set/delete it each time away is set or removed on server)
- irc: ignore join if nick is not self nick and if channel buffer does not exist ([bug #32667](https://savannah.nongnu.org/bugs/?32667))
- irc: fix crash when setting wrong value in option irc.server.xxx.sasl_mechanism ([bug #32670](https://savannah.nongnu.org/bugs/?32670))
- irc: fix crash when completing `/part` command on a non-irc buffer ([bug #32402](https://savannah.nongnu.org/bugs/?32402))
- irc: add many missing commands for target buffer (options irc.msgbuffer.xxx) ([bug #32216](https://savannah.nongnu.org/bugs/?32216))
- lua: fix crash when many scripts are executing callbacks at same time
- perl: fix memory leak when calling Perl functions ([bug #32895](https://savannah.nongnu.org/bugs/?32895))
- relay: fix crash on `/upgrade` when nick in irc client is not yet set
- relay: allow colon in server password received from client
- relay: do not send join for private buffers to client
- rmodifier: fix reload of file rmodifier.conf
- rmodifier: fix crash when adding rmodifier with invalid regex
- xfer: do not close chat buffers when removing xfer from list ([bug #32271](https://savannah.nongnu.org/bugs/?32271))

### Build

- tcl: fix Tcl detection on some 64-bits systems ([bug #32915](https://savannah.nongnu.org/bugs/?32915))

## Version 0.3.4 (2011-01-16)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add 256 colors support, new command `/color`, new section "palette" in weechat.conf ([task #6834](https://savannah.nongnu.org/task/?6834))
- core: add info "weechat_upgrading", signal "upgrade_ended", display duration of upgrade
- core: add new option weechat.look.highlight_regex and function string_has_highlight_regex in plugin API ([task #10321](https://savannah.nongnu.org/task/?10321))
- core: add new option weechat.look.hotlist_unique_numbers ([task #10691](https://savannah.nongnu.org/task/?10691))
- core: add property "hotlist_max_level_nicks" in buffers to set max hotlist level for some nicks in buffer
- core: add new options weechat.look.input_share and weechat.look.input_share_overwrite ([task #9228](https://savannah.nongnu.org/task/?9228))
- core: add new option weechat.look.prefix_align_min ([task #10650](https://savannah.nongnu.org/task/?10650))
- core: replace the 10 nick color options and number of nick colors by a single option weechat.color.chat_nick_colors (comma separated list of colors)
- core: add color support in option weechat.look.buffer_time_format
- api: add priority for hooks ([task #10550](https://savannah.nongnu.org/task/?10550))
- api: add new functions: list_search_pos, list_casesearch_pos, hashtable_get_string, hashtable_set_pointer, hook_info_hashtable, info_get_hashtable, hook_hsignal, hook_hsignal_send, hook_completion_get_string, nicklist_group_get_integer, nicklist_group_get_string, nicklist_group_get_pointer, nicklist_group_set, nicklist_nick_get_integer, nicklist_nick_get_string, nicklist_nick_get_pointer, nicklist_nick_set
- irc: add option `-server` in command `/join` ([task #10837](https://savannah.nongnu.org/task/?10837))
- irc: add option `-switch` in commands `/connect` and `/reconnect`
- irc: add command `/notify`, new options irc.look.notify_tags_ison, irc.look.notify_tags_whois, irc.network.notify_check_ison, irc.network.notify_check_whois, new option "notify" in servers, new infolist "irc_notify" ([task #5441](https://savannah.nongnu.org/task/?5441))
- irc: add new option irc.look.nick_color_force ([task #7374](https://savannah.nongnu.org/task/?7374))
- irc: add command redirection with hsignals irc_redirect_pattern and irc_redirect_command ([task #6703](https://savannah.nongnu.org/task/?6703))
- irc: add new options irc.color.nick_prefix and irc.color.nick_suffix
- irc: add new option irc.look.item_away_message
- irc: add tag "nick_xxx" in user messages
- irc: move options from network section to server section: connection_timeout, anti_flood_prio_high, anti_flood_prio_low, away_check, away_check_max_nicks, default_msg_part, default_msg_quit ([task #10664](https://savannah.nongnu.org/task/?10664), [task #10668](https://savannah.nongnu.org/task/?10668))
- irc: display old channel topic when topic is unset ([task #9780](https://savannah.nongnu.org/task/?9780))
- irc: add new info_hashtable "irc_parse_message"
- irc: add signal "irc_input_send"
- irc: rename options irc.look.open_channel_near_server and irc.look.open_pv_near_server to irc.look.new_channel_position and irc.look.new_pv_position with new values (none, next or near_server)
- rmodifier: new plugin "rmodifier": alter modifier strings with regular expressions ([bug #26964](https://savannah.nongnu.org/bugs/?26964))
- relay: beta version of IRC proxy, now relay plugin is compiled by default
- python: add info "python2_bin" (path to Python 2.x interpreter)

### Bug fixes

- core: fix scroll problem on buffers with free content and non-allocated lines ([bug #32039](https://savannah.nongnu.org/bugs/?32039))
- core: call to function hook_config when config option is created
- core: fix infinite loop on GnuTLS handshake when connecting with SSL to server on wrong port or server with SSL problems ([bug #27487](https://savannah.nongnu.org/bugs/?27487))
- core: fix data sent to callback of hook_process (some data was sometimes missing), use a 64KB buffer for child output and send data to callback only when buffer is full
- core: fix crash when displaying groups in buffer nicklist
- core: fix bug with message "day changed to", sometimes displayed several times wrongly
- core: fix default value of bar items options ([bug #31422](https://savannah.nongnu.org/bugs/?31422))
- core: fix bug with buffer name in `/bar scroll` command
- core: optimize incremental search in buffer: do not search anymore when chars are added to a text not found ([bug #31167](https://savannah.nongnu.org/bugs/?31167))
- core: fix memory leaks when removing item in hashtable and when setting highlight words in buffer
- core: use similar behavior for keys bound to local or global history ([bug #30759](https://savannah.nongnu.org/bugs/?30759))
- alias: complete with alias value for second argument of command `/alias`
- irc: differentiate notices from messages in private buffer ([bug #31980](https://savannah.nongnu.org/bugs/?31980))
- irc: update nick modes with message 221 ([bug #32038](https://savannah.nongnu.org/bugs/?32038))
- irc: fix bug with charset decoding on private buffers (decoding was made for local nick instead of remote nick) ([bug #31890](https://savannah.nongnu.org/bugs/?31890))
- irc: allow command `/reconnect` on servers that are not currently connected ([bug #30726](https://savannah.nongnu.org/bugs/?30726))
- irc: fix topic completion in command `/topic` when channel topic starts with channel name
- irc: improve nick prefixes, all modes (even unknown) are used with PREFIX value from message 005
- irc: fix crash/bug when option "addresses" for a server is unset or changed when WeeChat is connected to this server ([bug #31268](https://savannah.nongnu.org/bugs/?31268))
- irc: switch to next server address when IRC error is received after TCP connection but before message 001 ([bug #30884](https://savannah.nongnu.org/bugs/?30884))
- irc: fix bug with hostmasks in command `/ignore` ([bug #30716](https://savannah.nongnu.org/bugs/?30716))
- relay: split of messages sent to clients of irc proxy
- scripts: add missing function infolist_reset_item_cursor in API ([bug #31057](https://savannah.nongnu.org/bugs/?31057))
- lua: fix crash when unloading script
- xfer: fix dcc chat buffer name (use irc server in name) ([bug #29925](https://savannah.nongnu.org/bugs/?29925))
- xfer: fix dcc file transfer for large files (more than 4 GB) on 32-bit systems ([bug #31531](https://savannah.nongnu.org/bugs/?31531))
- xfer: fix bug at end of file sent, sometimes transfer is still active although file was successfully sent

### Build

- core: add support of Python 2.7 in CMake and configure ([debian #606989](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=606989))
- ruby: fix compilation with Ruby 1.9.2 ([patch #7316](https://savannah.nongnu.org/patch/?7316))

## Version 0.3.3 (2010-08-07)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: use "!" to reverse a regex in a filter (to keep lines matching regex and hide other lines) ([task #10032](https://savannah.nongnu.org/task/?10032))
- core: add keys for undo/redo changes on command line (default: `Ctrl`+`_` and `Alt`+`_`) ([task #9483](https://savannah.nongnu.org/task/?9483))
- core: add new option weechat.look.align_end_of_lines
- core: add new option weechat.look.confirm_quit
- core: add new option weechat.color.status_name_ssl ([task #10339](https://savannah.nongnu.org/task/?10339))
- core: add hashtables with new functions in plugin API
- api: add function string_expand_home, fix bug with replacement of home in paths
- irc: add new option irc.look.nick_color_stop_chars
- irc: add new options irc.look.display_host_join/join_local/quit and irc.color.reason_quit
- irc: add command `/wallchops`, fix bug with display of notice for ops ([task #10021](https://savannah.nongnu.org/task/?10021), [bug #29932](https://savannah.nongnu.org/bugs/?29932))
- irc: add isupport value in servers (content of IRC message 005), with new infos: irc_server_isupport and irc_server_isupport_value
- irc: add message in private buffer when nick is back on server after a `/quit`
- irc: add new options irc.network.autoreconnect_delay_growing and irc.network.autoreconnect_delay_max ([task #10338](https://savannah.nongnu.org/task/?10338))
- irc: add missing commands 346, 347 (channel invite list)
- irc: improve lag indicator: two colors (counting and finished), update item even when pong has not been received, lag_min_show is now in milliseconds
- irc: move options weechat.color.nicklist_prefix to irc plugin
- logger: use tag "no_log" to prevent a line from being written in log file

### Bug fixes

- core: fix bug with scroll_unread: do not scroll to a filtered line ([bug #29991](https://savannah.nongnu.org/bugs/?29991))
- core: fix crash with hook_process (when timer is called on a deleted hook process)
- core: fix display bug with special chars (ascii value below 32) ([bug #30602](https://savannah.nongnu.org/bugs/?30602))
- core: fix display bug with attributes like underlined in bars ([bug #29889](https://savannah.nongnu.org/bugs/?29889))
- api: fix bug with replacement char in function string_remove_color ([bug #30296](https://savannah.nongnu.org/bugs/?30296))
- irc: fix bug in parser when no argument is received after command, no callback was called, and message was silently ignored ([bug #30640](https://savannah.nongnu.org/bugs/?30640))
- irc: fix import of certificates created by OpenSSL ≥ 1.0.0 ([bug #30316](https://savannah.nongnu.org/bugs/?30316))
- irc: fix display of local SSL certificate when it is sent to server ([patch #7218](https://savannah.nongnu.org/patch/?7218))
- irc: use empty real name by default in config, instead of reading real name in /etc/passwd ([bug #30111](https://savannah.nongnu.org/bugs/?30111))
- irc: fix bug with command line option "irc://" ([bug #29990](https://savannah.nongnu.org/bugs/?29990)), new format for port and channels
- irc: fix display of messages 330 and 333 on some servers
- irc: fix bug with nick prefix "*" (chan founder) on some IRC servers ([bug #29890](https://savannah.nongnu.org/bugs/?29890))
- irc: fix bug with option irc.network.lag_check when value is 0 (zero)
- irc: try other nick when connecting to server and receiving message 437 (nick unavailable)
- irc: set buffer local variable "away" when opening new channel ([bug #29618](https://savannah.nongnu.org/bugs/?29618))
- fifo: fix bug with fifo pipe when setting fifo option to "on"
- xfer: fix bug with double quotes in DCC filenames ([bug #30471](https://savannah.nongnu.org/bugs/?30471))

## Version 0.3.2 (2010-04-18)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add new options for command `/key`: `listdefault`, `listdiff` and `reset`
- core: add new command `/mute`
- core: add command line option `-s` (or `--no-script`) to start WeeChat without loading any script
- core: improve plugins autoload (option weechat.plugin.autoload): allow to use "*" as wildcard and "!" to prevent a plugin from being autoloaded ([task #6361](https://savannah.nongnu.org/task/?6361))
- core: add option "switch_active_buffer_previous" in command `/input` ([task #10141](https://savannah.nongnu.org/task/?10141))
- core: add new option weechat.look.time_format to customize default format for date/time displayed (localized date by default), add function util_get_time_string in plugin API ([patch #6914](https://savannah.nongnu.org/patch/?6914))
- core: add new option weechat.look.command_chars, add functions string_is_command_char and string_input_for_buffer in plugin and script API
- core: add new option weechat.look.read_marker_always_show
- api: add "version_number" for function info_get to get WeeChat version as number
- api: add "irc_is_nick" for function info_get to check if a string is a valid IRC nick name ([patch #7133](https://savannah.nongnu.org/patch/?7133))
- api: add functions string_encode_base64 and string_decode_base64, fix bug with base64 encoding
- api: add functions string_match, string_has_highlight and string_mask_to_regex in script plugin API
- api: add description of arguments for functions hook_info and hook_infolist
- api: add signals "day_changed", "nicklist_group_added/removed", "nicklist_nick_added/removed"
- alias: add custom completion for aliases ([task #9479](https://savannah.nongnu.org/task/?9479))
- scripts: allow script commands to reload only one script
- irc: add SASL authentication, with PLAIN and DH-BLOWFISH mechanisms ([task #8829](https://savannah.nongnu.org/task/?8829))
- irc: add new option irc.look.part_closes_buffer to close buffer when `/part` is issued on channel ([task #10295](https://savannah.nongnu.org/task/?10295))
- irc: add option `-open` in command `/connect`
- irc: add option irc.network.connection_timeout (timeout between TCP connection to server and reception of message 001)
- irc: add options irc.look.smart_filter_join and irc.look.smart_filter_quit
- irc: add option irc.look.item_channel_modes_hide_key to hide channel key in channel modes ([bug #23961](https://savannah.nongnu.org/bugs/?23961))
- irc: add option irc.look.item_nick_prefix
- irc: add command `/map`
- irc: add missing commands 276, 343
- logger: allow date format in logger options path and mask ([task #9430](https://savannah.nongnu.org/task/?9430))
- xfer: add signal "xfer_ended" ([patch #7081](https://savannah.nongnu.org/patch/?7081))

### Bug fixes

- core: remove unneeded space after time on each line if option weechat.look.buffer_time_format is set to empty value ([bug #28751](https://savannah.nongnu.org/bugs/?28751))
- core: use arguments for infolist "nicklist" to return only one nick or group
- core: fix bug with writing of configuration files when disk is full ([bug #29331](https://savannah.nongnu.org/bugs/?29331))
- core: fix infinite loop with `/layout apply` and bug when applying layout, sometimes many `/layout apply` were needed ([bug #26110](https://savannah.nongnu.org/bugs/?26110))
- gui: refresh screen when exiting WeeChat (to display messages printed after `/quit`)
- gui: fix bug with global history, reset pointer to last entry after each user input ([bug #28754](https://savannah.nongnu.org/bugs/?28754))
- gui: fix bug with bar background after text with background color ([bug #28157](https://savannah.nongnu.org/bugs/?28157))
- gui: fix bug with cursor when position is last char of terminal
- api: add missing infos in functions buffer_get_{integer|string} and in buffer infolist
- api: fix function color in Lua script API
- api: fix "inactivity" value when no key has been pressed since WeeChat started ([bug #28930](https://savannah.nongnu.org/bugs/?28930))
- api: return absolute path for info_get of "weechat_dir" ([bug #27936](https://savannah.nongnu.org/bugs/?27936))
- scripts: fix bug with callbacks when loading a script already loaded
- perl: fix crash when multiplicity is disabled
- perl: fix crash when callbacks are called during script initialization ([bug #29018](https://savannah.nongnu.org/bugs/?29018))
- perl: fix crash on `/quit` or unload of plugin under FreeBSD and Cygwin ([bug #29467](https://savannah.nongnu.org/bugs/?29467))
- perl: fix bug with script filename when multiplicity is disabled ([bug #29530](https://savannah.nongnu.org/bugs/?29530))
- irc: fix crash with SSL connection if option ssl_cert is set ([bug #28752](https://savannah.nongnu.org/bugs/?28752))
- irc: fix bug with SSL connection (fails sometimes when ssl_verify is on) ([bug #28741](https://savannah.nongnu.org/bugs/?28741))
- irc: fix bug with nicks on reconnection: try all nicks in list, even if nick used was not the first in list of nicks
- irc: fix command `/list`: send channel and server name given as argument, and use separate option `-re` to allow a regex
- irc: fix PART message received on Undernet server ([bug #28825](https://savannah.nongnu.org/bugs/?28825))
- irc: fix bug with `/away -all`: set or unset future away for disconnected servers ([bug #29022](https://savannah.nongnu.org/bugs/?29022))
- irc: fix bug with prefix "!" for mode "a" (channel admin) ([bug #29109](https://savannah.nongnu.org/bugs/?29109))
- irc: do not send signals "irc_in" and "irc_in2" when messages are ignored, add new signals "irc_raw_in" and "irc_raw_in2"
- irc: apply smart filter only on channels, not private buffers ([bug #28841](https://savannah.nongnu.org/bugs/?28841))
- xfer: fix crash when purging old xfer chats ([bug #28764](https://savannah.nongnu.org/bugs/?28764))

### Build

- irc: fix compilation with old GnuTLS versions ([bug #28723](https://savannah.nongnu.org/bugs/?28723))

## Version 0.3.1.1 (2010-01-31)

### Bug fixes

- irc: fix crash with SSL connection if option ssl_cert is set ([bug #28752](https://savannah.nongnu.org/bugs/?28752))
- irc: fix bug with SSL connection (fails sometimes when ssl_verify is on) ([bug #28741](https://savannah.nongnu.org/bugs/?28741))
- xfer: fix crash when purging old xfer chats ([bug #28764](https://savannah.nongnu.org/bugs/?28764))

### Build

- irc: fix compilation with old GnuTLS versions ([bug #28723](https://savannah.nongnu.org/bugs/?28723))

## Version 0.3.1 (2010-01-23)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add option "grab_key_command" in command `/input` (bound by default to `Alt`+`k`)
- alias: new expansions for alias arguments ($n, $-m, $n-, $n-m, $*, $~) ([patch #6917](https://savannah.nongnu.org/patch/?6917))
- alias: allow use of wildcards for `/alias list` ([patch #6925](https://savannah.nongnu.org/patch/?6925))
- alias: allow `/unalias` to remove multiple aliases ([patch #6926](https://savannah.nongnu.org/patch/?6926))
- irc: add new commands `/allchan` and `/allserv` with excluding option, commands `/ame` and `/amsg` are now aliases, new aliases `/aaway` and `/anick`
- irc: add options to customize target buffer for messages ([task #7381](https://savannah.nongnu.org/task/?7381))
- irc: add new output queue for messages with low priority (like automatic CTCP replies), high priority is given to user messages or commands
- irc: use self-signed certificate to auto identify on IRC server (CertFP) ([task #7492](https://savannah.nongnu.org/task/?7492), [debian #453348](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=453348))
- irc: check SSL certificates ([task #7492](https://savannah.nongnu.org/task/?7492))
- irc: add option "autorejoin_delay" for servers ([task #8771](https://savannah.nongnu.org/task/?8771))
- irc: add option to use same nick color in channel and private ([task #9870](https://savannah.nongnu.org/task/?9870))
- irc: add missing command 275 ([patch #6952](https://savannah.nongnu.org/patch/?6952))
- irc: add commands `/sajoin`, `/samode`, `/sanick`, `/sapart`, `/saquit` ([task #9770](https://savannah.nongnu.org/task/?9770))
- irc: add options for CTCP, to block/customize CTCP reply ([task #9693](https://savannah.nongnu.org/task/?9693))
- irc: add missing CTCP: clientinfo, finger, source, time, userinfo ([task #7270](https://savannah.nongnu.org/task/?7270))
- irc: add all server options for commands `/server` and `/connect`
- irc: add arguments for command `/rehash`
- irc: improve mask used by command `/kickban`
- xfer: add color for nicks in chat
- xfer: add missing command `/me` ([bug #28658](https://savannah.nongnu.org/bugs/?28658))
- gui: add color "darkgray", add support for background with light color

### Bug fixes

- core: fix bug with script installation on BSD/macOS ([patch #6980](https://savannah.nongnu.org/patch/?6980))
- core: fix compilation under Cygwin ([patch #6916](https://savannah.nongnu.org/patch/?6916))
- core: fix plural form in translation files ([bug #27430](https://savannah.nongnu.org/bugs/?27430))
- core: fix terminal title bug: do not reset it when option weechat.look.set_title is off ([bug #27399](https://savannah.nongnu.org/bugs/?27399))
- core: fix buffer used by some input functions called via plugin API with buffer pointer ([bug #28152](https://savannah.nongnu.org/bugs/?28152))
- alias: fix bug with buffer for execution of alias, when called from plugin API with function command ([bug #27697](https://savannah.nongnu.org/bugs/?27697))
- alias: fix bug with arguments ([bug #27440](https://savannah.nongnu.org/bugs/?27440))
- irc: improve error management on socket error (recv/send)
- irc: fix nick color for nicks with wide chars ([bug #28547](https://savannah.nongnu.org/bugs/?28547))
- irc: fix autorejoin on channels with key
- irc: fix command `/connect` (options -ssl, -ipv6 and -port) ([bug #27486](https://savannah.nongnu.org/bugs/?27486))
- xfer: add missing charset decoding/encoding for IRC DCC chat ([bug #27482](https://savannah.nongnu.org/bugs/?27482))
- fifo: remove old pipes before creating new pipe
- gui: fix color "black" ([bug #23882](https://savannah.nongnu.org/bugs/?23882), [debian #512957](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=512957))
- gui: fix message "Day changed to", sometimes displayed at wrong time ([bug #26959](https://savannah.nongnu.org/bugs/?26959))
- gui: fix bug with URL selection in some terminals (caused by horizontal lines) ([bug #27700](https://savannah.nongnu.org/bugs/?27700))
- gui: use default auto completion for arguments of unknown commands
- gui: fix alignment problem for buffer name when a merged buffer is closed ([bug #27617](https://savannah.nongnu.org/bugs/?27617))
- gui: update hotlist when a buffer is closed ([bug #27470](https://savannah.nongnu.org/bugs/?27470)), remove buffer from hotlist when buffer is cleared ([bug #27530](https://savannah.nongnu.org/bugs/?27530))
- gui: fix `/input history_global_next`: reset input content when last command in history is reached
- api: fix function bar_set for python/lua/ruby ([patch #6912](https://savannah.nongnu.org/patch/?6912))

### Build

- core: fix CMake directories: let user customize lib, share, locale and include directories ([patch #6922](https://savannah.nongnu.org/patch/?6922))
- ruby: add support of Ruby ≥ 1.9.1 ([patch #6989](https://savannah.nongnu.org/patch/?6989))

## Version 0.3.0 (2009-09-06)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- core: add group support in nicklist
- core: add `/reload` command to reload WeeChat and plugins config files (signal SIGHUP is caught to reload config files)
- core: add new `/layout` command and save_layout_on_exit config option, to save/restore windows and buffers order ([task #5453](https://savannah.nongnu.org/task/?5453))
- core: add new options for completion, optional stop instead of cycling with words found ([task #5909](https://savannah.nongnu.org/task/?5909))
- core: new name for configuration files (*.conf instead of *.rc)
- core: improve `/set` command, new command `/unset` ([task #6085](https://savannah.nongnu.org/task/?6085))
- core: add new input action "set_unread_current_buffer" to set unread marker for current buffer only ([task #7286](https://savannah.nongnu.org/task/?7286))
- core: remove key functions, replaced by `/input` command
- core: add argument with buffer number/range for command `/buffer close` ([task #9390](https://savannah.nongnu.org/task/?9390), [task #7239](https://savannah.nongnu.org/task/?7239))
- core: add new command `/wait` (schedule a command execution in future)
- core: improve main loop: higher timeout in select, less CPU usage
- gui: new display engine, with prefix and message for each line
- gui: add new type of buffer, with free content
- gui: add tags for lines and custom filtering by tags or regex ([task #7674](https://savannah.nongnu.org/task/?7674))
- gui: add buffer merging ([task #7404](https://savannah.nongnu.org/task/?7404))
- gui: add custom bars, with custom items
- gui: add key to zoom a window ([task #7470](https://savannah.nongnu.org/task/?7470))
- gui: add keys to move into last visited buffers: `Alt`+`<` and `Alt`+`>`
- gui: come back to last visited buffer when closing a buffer
- gui: add new option scroll_page_percent to choose percent of height to scroll with `PgUp` and `PgDn` keys ([task #8702](https://savannah.nongnu.org/task/?8702))
- gui: add number of lines remaining after last line displayed in "-MORE-" indicator ([task #6702](https://savannah.nongnu.org/task/?6702))
- network: add support for more than one proxy, with proxy selection for each IRC server ([task #6859](https://savannah.nongnu.org/task/?6859))
- aspell: improve plugin: use of many dictionaries, global dictionary, real time checking (optional), fix bugs with utf-8
- irc: add irc plugin (replaces old IRC code in core) ([task #6217](https://savannah.nongnu.org/task/?6217))
- irc: add smart join/part/quit message filter ([task #8503](https://savannah.nongnu.org/task/?8503))
- irc: use of many addresses for servers (auto-switch when a connection fails), nicks are now set with one option "nicks" ([task #6088](https://savannah.nongnu.org/task/?6088))
- irc: add some colors in messages from server (for text and nicks) ([task #8926](https://savannah.nongnu.org/task/?8926))
- irc: add color decoding in title for IRC channels ([task #6030](https://savannah.nongnu.org/task/?6030))
- irc: add missing commands (328, 369)
- logger: add logger plugin with new features: backlog, level for messages to log ([task #8592](https://savannah.nongnu.org/task/?8592)), level by buffer ([task #6687](https://savannah.nongnu.org/task/?6687)), filename mask by buffer, option "name_lower_case" ([bug #19522](https://savannah.nongnu.org/bugs/?19522))
- relay: add relay plugin (network communication between WeeChat and remote application)
- xfer: add speed limit for DCC files sending ([task #6178](https://savannah.nongnu.org/task/?6178))
- xfer: add new option xfer.file.use_nick_in_filename for Xfer files ([task #7140](https://savannah.nongnu.org/task/?7140))
- plugins: add some other plugins: alias, demo, fifo, tcl, xfer
- scripts: new scripts: weeget.py (script manager), jabber.py (jabber/XMPP protocol), go.py (quick jump to buffers), buffers.pl (sidebar with list of buffers), iset.pl (set options interactively), weetris.pl (tetris-like game), mastermind.pl, ...
- api: add hooks: command, timer, file descriptor, process, connection, print, signal, config, completion, modifier, info, infolist
- api: new plugin API with many new functions: hooks, buffer management and nicklist, bars, configuration files, network, infos/infolists, lists, upgrade

### Internationalization

- add Polish translations

### Bug fixes

- core: fix nick completion bug (missing space after nick)
- gui: fix completion with non-latin nicks ([bug #18993](https://savannah.nongnu.org/bugs/?18993))
- gui: fix display bug with some weird UTF-8 chars ([bug #19687](https://savannah.nongnu.org/bugs/?19687))
- gui: fix bug with wide chars in input ([bug #16356](https://savannah.nongnu.org/bugs/?16356))
- gui: fix bug when switching window, scrollback is now preserved ([task #7680](https://savannah.nongnu.org/task/?7680))
- network: fix network connection for hostnames resolving to several IPs: try all IPs in list until one succeeds ([bug #21473](https://savannah.nongnu.org/bugs/?21473), [debian #498610](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=498610))
- alias: fix bug with alias, use current buffer to run commands ([bug #22876](https://savannah.nongnu.org/bugs/?22876))
- irc: fix lock with SSL servers when connection fails, and when disconnecting during connection problem ([bug #17584](https://savannah.nongnu.org/bugs/?17584))
- irc: command `/whois` is now authorized in private without argument ([task #7482](https://savannah.nongnu.org/task/?7482))
- irc: fix private buffer name with Irssi proxy ([bug #26589](https://savannah.nongnu.org/bugs/?26589))
- irc: remove kernel info in CTCP VERSION reply ([task #7494](https://savannah.nongnu.org/task/?7494))
- irc: fix mode parsing when receiving modes with arguments ([bug #26793](https://savannah.nongnu.org/bugs/?26793))
- scripts: do not auto-load hidden files ([bug #21390](https://savannah.nongnu.org/bugs/?21390))

## Version 0.2.6.3 (2009-06-13)

### Bug fixes

- fix GnuTLS detection (use pkg-config instead of libgnutls-config) ([bug #26790](https://savannah.nongnu.org/bugs/?26790))

## Version 0.2.6.2 (2009-04-18)

### Bug fixes

- fix bug with charset decoding (for example with iso2022jp) ([bug #26228](https://savannah.nongnu.org/bugs/?26228))

## Version 0.2.6.1 (2009-03-14)

### Bug fixes

- fix crash with some special chars in IRC messages ([bug #25862](https://savannah.nongnu.org/bugs/?25862), [CVE-2009-0661](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2009-0661))

## Version 0.2.6 (2007-09-06)

### New features

- add new option `deloutq` to `/server` command to delete all servers messages out queues ([task #7221](https://savannah.nongnu.org/task/?7221))
- add string length limit for setup file options
- add option to align text of messages (except first lines) ([task #7246](https://savannah.nongnu.org/task/?7246))
- add paste detection, new options look_paste_max_lines and col_input_actions ([task #5442](https://savannah.nongnu.org/task/?5442))
- add support of channel mode +u (channel user) ([bug #20717](https://savannah.nongnu.org/bugs/?20717))
- improve `/connect` command to connect to a host by creating a temporary server, add option to `/server` to create temporary server ([task #7095](https://savannah.nongnu.org/task/?7095))
- add `copy`, `rename` and `keep` options to `/server` command
- allow clear of multiple selected buffers with `/clear` ([patch #6112](https://savannah.nongnu.org/patch/?6112))
- add key for setting unread marker on all buffers (default: `Ctrl`+`s`, `Ctrl`+`u`) ([task #7180](https://savannah.nongnu.org/task/?7180))
- improve command `/server` ant its output
- add 3 default new keys: `Ctrl`+`b` (left), `Ctrl`+`f` (right), `Ctrl`+`d` (delete)
- add "buffer_move" event handler to plugins API ([task #6708](https://savannah.nongnu.org/task/?6708))
- add key function "jump_previous_buffer" to jump to buffer previously displayed (new key: `Alt`+`j`, `Alt`+`p`) ([task #7085](https://savannah.nongnu.org/task/?7085))
- add "%*" to completion template, to repeat last completion
- add `-nojoin` option for `/connect` and `/reconnect` commands ([task #7074](https://savannah.nongnu.org/task/?7074))
- add `scroll` option to `/buffer` command
- down key now saves input to history and clears input line ([task #7049](https://savannah.nongnu.org/task/?7049))
- command `/away` allowed when not connected to server (internally stored and AWAY command is sent when connecting to server) ([task #7003](https://savannah.nongnu.org/task/?7003))
- add argument for `/upgrade` command (path to binary)
- add hotlist sort with new option "look_hotlist_sort" ([task #5870](https://savannah.nongnu.org/task/?5870))

### Bug fixes

- fix bug with log of plugin messages (option log_plugin_msg)
- fix display bug with some special chars in messages (some words were truncated on screen) ([bug #20944](https://savannah.nongnu.org/bugs/?20944))
- fix UTF-8 bug with color encoding/decoding
- fix crash when searching text in buffer with `Ctrl`+`r` ([bug #20938](https://savannah.nongnu.org/bugs/?20938))
- fix bug with flock when home is on NFS filesystem ([bug #20913](https://savannah.nongnu.org/bugs/?20913))
- fix user modes in nicklist when ban and nick mode are received in the same MODE message ([bug #20870](https://savannah.nongnu.org/bugs/?20870))
- fix IRC message 333: silently ignore message if error when parsing it
- fix server option "command_delay": does not freeze WeeChat anymore
- fix bug with highlight and UTF-8 chars around word ([bug #20753](https://savannah.nongnu.org/bugs/?20753))
- fix nick prefix display on servers that doesn't support all prefixes ([bug #20025](https://savannah.nongnu.org/bugs/?20025))
- fix terminal encoding detection when NLS is disabled ([bug #20646](https://savannah.nongnu.org/bugs/?20646))
- fix crash when sending data to channel or pv on disconnected server ([bug #20524](https://savannah.nongnu.org/bugs/?20524))
- fix bugs with IRC color in messages, now color codes are inserted in command line with `Ctrl`+`c`, `Ctrl`+`b` instead of `%C,%B` ([bug #20222](https://savannah.nongnu.org/bugs/?20222), [task #7060](https://savannah.nongnu.org/task/?7060))
- fix bug with smart nick completion (last speakers first) when a nick is changed
- fix charset bug with channel names in status bar ([bug #20400](https://savannah.nongnu.org/bugs/?20400))
- fix log file when channel name contains "/" ([bug #20072](https://savannah.nongnu.org/bugs/?20072))
- fix bug with `/topic` when channel not open and topic not defined ([bug #20141](https://savannah.nongnu.org/bugs/?20141))

### Documentation

- add Swedish quickstart guide

## Version 0.2.5 (2007-06-07)

### New features

- add missing IRC commands (327, 378, 379) ([bug #20091](https://savannah.nongnu.org/bugs/?20091))
- add "%M" for completion with nicks of current server (nicks on open channels) ([task #6931](https://savannah.nongnu.org/task/?6931))
- improve key bindings: now possible to bind a key on many commands, separated by semicolon ([task #5444](https://savannah.nongnu.org/task/?5444))
- improve IRC long message split: use word boundary ([task #6685](https://savannah.nongnu.org/task/?6685))
- add protocol priority for GnuTLS ([patch #5915](https://savannah.nongnu.org/patch/?5915))
- add channel admin mode "!" for some IRC servers
- add `/reconnect` command ([task #5448](https://savannah.nongnu.org/task/?5448))
- add `-all` option for `/connect` and `/disconnect` commands ([task #6232](https://savannah.nongnu.org/task/?6232))
- improve nick completion: completion with last speakers first and self nick at the end; add option look_nick_completion_smart, enabled by default ([task #5896](https://savannah.nongnu.org/task/?5896))
- add color for input text not found in buffer history

### Bug fixes

- fix `/quote` command: now allowed when socket is OK (even if IRC connection to server is not OK) ([bug #20113](https://savannah.nongnu.org/bugs/?20113))
- fix hotlist when exiting search mode: current buffer is removed from hotlist
- remove ":" for unknown IRC commands before arguments ([bug #19929](https://savannah.nongnu.org/bugs/?19929))
- fix "%C" completion: now completes with all channels of all servers
- fix bug with `/buffer query_name`, add server and channel completion for `/buffer` command ([bug #19928](https://savannah.nongnu.org/bugs/?19928))
- fix IRC mode parsing when receiving modes with arguments ([bug #19902](https://savannah.nongnu.org/bugs/?19902))
- fix crash with IRC JOIN malformed message ([bug #19891](https://savannah.nongnu.org/bugs/?19891))
- fix bug with nick prefixes on some IRC servers ([bug #19854](https://savannah.nongnu.org/bugs/?19854))
- improve setup file save: now writes temporary file, then rename it ([task #6847](https://savannah.nongnu.org/task/?6847))
- fix bug with $nick/$channel/$server variables in commands
- forget current nick when user manually disconnects from server
- fix nick display in input window
- fix bug with erroneous nickname when connecting to server ([bug #19812](https://savannah.nongnu.org/bugs/?19812))
- fix display bugs in IRC error messages
- fix bug with iso2022jp locale ([bug #18719](https://savannah.nongnu.org/bugs/?18719))
- fix string format bug when displaying string through plugin script API
- fix nick completion in command arguments ([bug #19590](https://savannah.nongnu.org/bugs/?19590))
- fix possible crash with nick completion when a nick leaves channel ([bug #19589](https://savannah.nongnu.org/bugs/?19589))
- fix USER message when connecting to IRC server ([patch #5835](https://savannah.nongnu.org/patch/?5835))

### Build

- add CMake for weechat compilation ([patch #5943](https://savannah.nongnu.org/patch/?5943))

## Version 0.2.4 (2007-03-29)

### New features

- rename log file for DCC chat (now <server>.dcc.<nick>.weechatlog)
- add current buffer in hotlist when scrolling up in buffer ([task #6664](https://savannah.nongnu.org/task/?6664))
- improve password hiding, code cleanup ([bug #19229](https://savannah.nongnu.org/bugs/?19229))
- add new return code in plugin API to force highlight (for message handlers only)
- add `call` option to `/key` command, add new key function "insert" to insert text on command line ([task #6468](https://savannah.nongnu.org/task/?6468))
- add event handler to plugin API
- add numeric argument for `/clear` command (buffer number) ([patch #5372](https://savannah.nongnu.org/patch/?5372))
- add new key (`Ctrl`+`r`) for interactive and incremental search in buffer history ([task #6628](https://savannah.nongnu.org/task/?6628))

### Bug fixes

- fix color bug with IRC messages displayed by plugins ([bug #19442](https://savannah.nongnu.org/bugs/?19442))
- fix topic charset, now using channel charset if defined ([bug #19386](https://savannah.nongnu.org/bugs/?19386))
- fix crash when closing a pv if a DCC chat is open on same nick ([bug #19147](https://savannah.nongnu.org/bugs/?19147))
- fix bug with channel topic after reconnection (not erased) ([bug #19384](https://savannah.nongnu.org/bugs/?19384))
- fix bug with explode_string / free_exploded_string when max_items > 0
- fix `/topic` completion when no topic set on current channel ([bug #19322](https://savannah.nongnu.org/bugs/?19322))
- fix bug with server buffer when "look_one_server_buffer" is ON and server buffer is moved to any number > 1 ([bug #19219](https://savannah.nongnu.org/bugs/?19219))
- fix `/help` command: displays plugin help for redefined commands ([bug #19166](https://savannah.nongnu.org/bugs/?19166))
- prefix "/" disabled in commands ([patch #5769](https://savannah.nongnu.org/patch/?5769))
- fix completion of redefined commands removed by plugins ([bug #19176](https://savannah.nongnu.org/bugs/?19176))
- fix memory leaks in perl and python plugins ([bug #19163](https://savannah.nongnu.org/bugs/?19163))
- fix permissions on "dcc" and "logs" directories ([bug #18978](https://savannah.nongnu.org/bugs/?18978))
- fix crash when `/away` command is issued with no server connection ([bug #18839](https://savannah.nongnu.org/bugs/?18839))
- fix crash when closing a buffer opened on many windows
- fix freeze with SSL server when disconnecting after connection loss ([bug #18735](https://savannah.nongnu.org/bugs/?18735))

### Documentation

- add Scots quickstart guide

## Version 0.2.3 (2007-01-10)

### Bug fixes

- fix display bugs with nicklist at top/bottom when look_nicklist_separator is OFF ([bug #18737](https://savannah.nongnu.org/bugs/?18737))
- fix iconv problem, causing truncated words when using iso locale
- fix topic scroll when topic has multi-bytes chars
- fix bugs with charset: now decodes/encodes nicks and channels in IRC messages ([bug #18716](https://savannah.nongnu.org/bugs/?18716))

### Build

- fix compilation problem with iconv under FreeBSD

## Version 0.2.2 (2007-01-06)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- add anti-flood option (irc_anti_flood) ([task #5442](https://savannah.nongnu.org/task/?5442))
- plugins: "add_message_handler" now accepts "*" for all IRC messages
- add keys (`F9` / `F10`) to scroll topic ([task #6030](https://savannah.nongnu.org/task/?6030))
- add auto completion with channels and filenames ([task #5423](https://savannah.nongnu.org/task/?5423))
- add option "look_nicklist_separator" ([task #5437](https://savannah.nongnu.org/task/?5437))
- add "irc_send_unknown_commands" option to send unknown commands to IRC server (OFF by default) ([task #5947](https://savannah.nongnu.org/task/?5947))
- `/charset` command and charset conversions now made by "charset" plugin
- add filename completion ([task #5425](https://savannah.nongnu.org/task/?5425))
- add "modifier" in plugins API
- improve `/plugin` command
- add date in plugin function get_buffer_data
- add more values for config boolean values: y/true/t/1 and n/false/f/0

### Bug fixes

- fix bug with status bar (missing refresh) when closing a buffer
- fix bug with use of first buffer for a channel if not connected to server (now allowed only for a server buffer)
- fix refresh bug with private buffer title
- fix bug with nick completion in command arguments (now uses option look_nick_completion_ignore)
- fix display bug with color for first line on screen ([bug #17719](https://savannah.nongnu.org/bugs/?17719))
- fix bug with set_config function in plugins API ([bug #18448](https://savannah.nongnu.org/bugs/?18448))
- fix memory leak in keyboard input
- fix refresh bug when changing config options if window is split
- add space between chat and nicklist when position is "right" ([bug #17852](https://savannah.nongnu.org/bugs/?17852))
- fix bug with DCC SEND when filename begins with "~"
- fix display bug in status bar, wrong length when using UTF-8
- fix bug with ignore: now any IRC command is allowed
- fix crash with `Ctrl`+`t` (transpose) and one char on line ([bug #18153](https://savannah.nongnu.org/bugs/?18153))
- fix bug on ignore with "mode" IRC command ([bug #18058](https://savannah.nongnu.org/bugs/?18058))
- fix crash when loading ruby script if file does not exist, with Ruby ≥ 1.9 only ([bug #18064](https://savannah.nongnu.org/bugs/?18064))
- mode changes with `/op`, `/deop`, `/voice`, `/devoice`, `/halfop`, `/dehalfop` are now sent in one mode command to server ([task #5968](https://savannah.nongnu.org/task/?5968))
- fix bug with `/alias` and arguments (like $1), now text after argument(s) is used ([bug #17944](https://savannah.nongnu.org/bugs/?17944))
- fix minor display bug with special chars on some arch like PPC

### Build

- fix some portability bugs ([patch #5271](https://savannah.nongnu.org/patch/?5271))
- fix iconv detection for BSD ([patch #5456](https://savannah.nongnu.org/patch/?5456))
- fix typo in configure.in (bash specific test) ([patch #5450](https://savannah.nongnu.org/patch/?5450))

## Version 0.2.1 (2006-10-01)

### New features

- command `/away -all` now allowed when not connected to current server
- new signals handled: SIGTERM and SIGHUP (received when terminal is closed): clean WeeChat quit (send quit to irc servers then quit WeeChat)
- add some new default key bindings for existing keys (for some OS)
- command `/key` now OK with one argument (key name): display key if found
- add current channel completion for `/ctcp` command
- values yes/no accepted (as on/off) for config boolean values ([task #5454](https://savannah.nongnu.org/task/?5454))
- add server default notify level (set by `/buffer notify` on server buffer) ([task #5634](https://savannah.nongnu.org/task/?5634))
- add special vars $nick/$channel/$server for server_command, alias and plugin command handlers
- add arguments $1,$2,..,$9 and $* for alias ([task #5831](https://savannah.nongnu.org/task/?5831))
- add hotlist in session file when using `/upgrade` command ([task #5449](https://savannah.nongnu.org/task/?5449))

### Bug fixes

- fix crash for DCC receiver when resuming a file ([bug #17885](https://savannah.nongnu.org/bugs/?17885))
- fix DCC error for sender when receiver cancels DCC ([bug #17838](https://savannah.nongnu.org/bugs/?17838))
- fix random crash with `/upgrade` command (error when loading buffers)
- fix buffer search by server/channel: now if only channel is specified, a channel of another server can be found
- fix highlight for DCC, invite and notice: when a window is displaying buffer, there's no highlight
- fix bug with CTCP VERSION sent on channels ([bug #17547](https://savannah.nongnu.org/bugs/?17547))
- fix bugs in get_buffer_data which breaks the retrieval of buffer content (perl, lua)
- fix nicklist display bug when top/bottom (not enough lines) ([bug #17537](https://savannah.nongnu.org/bugs/?17537))
- fix bug with auto-rejoin of keyed channels ([bug #17534](https://savannah.nongnu.org/bugs/?17534))
- add default nick completion when line starts with "//" ([bug #17535](https://savannah.nongnu.org/bugs/?17535))
- fix crashes with `/buffer` and `/charset` commands when not connected to any server ([bug #17525](https://savannah.nongnu.org/bugs/?17525))
- fix nick refresh problem with unrealircd specific modes: chan owner (~) and chan admin (&) ([bug #17340](https://savannah.nongnu.org/bugs/?17340))

## Version 0.2.0 (2006-08-19)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- add "C"lear option on IRC raw buffer
- IRC raw buffer now uses join/part prefix with color to display messages
- add send of "quit" message to server when using `/disconnect`
- add "%m" for completion with self nick (on current server)
- add missing IRC commands (310, 326, 329, 338)
- improve DCC speed (up to x5 on LAN) by forking for DCC files and a new option "dcc_fast_send" (does not wait for ACK) ([task #5758](https://savannah.nongnu.org/task/?5758))
- add "look_save_on_exit" option (patch from Emanuele Giaquinta)
- add new functions in plugin/script API: get window info, get buffer info, get buffer content
- add color encoding for some commands like `/me`
- add aspell plugin

### Bug fixes

- fix "wallops" command when received, now displayed by WeeChat ([bug #17441](https://savannah.nongnu.org/bugs/?17441))
- fix `/wallops` command (now many words are correctly sent)
- fix command 348 (channel exception list, received by `/mode #chan e`)
- add missing modes (channel & user), now all modes are allowed ([bug #16606](https://savannah.nongnu.org/bugs/?16606))
- fix DCC restore after `/upgrade` (order is now correctly saved)
- fix away after server disconnection (now away is set again when reconnecting) ([bug #16359](https://savannah.nongnu.org/bugs/?16359))
- fix DCC file connection problem (connection from receiver to sender)
- fix crash when purging DCC with high number of DCC (> window size)
- fix completion for command handlers (now empty completion_template means nick completion, "-" string means no completion at all)
- fix nick alignment problem when look_nickmode is off
- add generic function for incoming numeric IRC commands ([bug #16611](https://savannah.nongnu.org/bugs/?16611))
- fix crash when doing `/part something` on a server buffer ([bug #17201](https://savannah.nongnu.org/bugs/?17201))
- charsets are now checked when set by `/charset` command
- fix crash on DCC buffer under Darwin 8 ([bug #17115](https://savannah.nongnu.org/bugs/?17115))
- fix bug with spaces in script names ([bug #16957](https://savannah.nongnu.org/bugs/?16957))
- fix random crash when "MODE #chan -l" is received
- fix bug in IRC parser (random crash with malformed IRC messages)
- fix refresh bugs when terminal is resized: too many refreshes, display bug with split windows
- case ignored for channel names in charset options ([bug #16858](https://savannah.nongnu.org/bugs/?16858))
- fix crash when setting look_one_server_buffer to ON ([bug #16932](https://savannah.nongnu.org/bugs/?16932))
- fix display bug with special char ([bug #16732](https://savannah.nongnu.org/bugs/?16732))
- rename plugins names (remove "lib" prefix in name)
- fix crash when closing DCC/raw buffer if 2 are open ([bug #16808](https://savannah.nongnu.org/bugs/?16808))
- fix crashes with DCC chat remove/purge on DCC view ([bug #16775](https://savannah.nongnu.org/bugs/?16775))
- fix bug with connection to bnc ([bug #16760](https://savannah.nongnu.org/bugs/?16760))
- command `/save` now writes plugins options (~/.weechat/plugins.rc)
- fix crash with register function in plugin scripts ([bug #16701](https://savannah.nongnu.org/bugs/?16701))
- fix random crash at exit (`/quit` or `/upgrade`) with split windows

### Documentation

- add Polish, Russian and Czech quickstart guide

### Build

- add configure option for doc XSL prefix ([bug #16991](https://savannah.nongnu.org/bugs/?16991))

## Version 0.1.9 (2006-05-25)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- add backtrace when WeeChat crashes, log file automatically renamed
- add new key to find previous completion (`Shift`+`Tab` by default)
- add missing IRC commands (006, 007, 290, 292, 310, 379, 437, 974)
- add new option to customize input prompt
- add nick modes
- add hostnames associated to nicks (available for `/ban` completion)
- add "+p" mode for channels, fix mode display in status bar
- add nick alignment options
- add keyboard handler to plugin API
- improve script plugin loader
- add hostname/IP option for connection to server
- add `/setp` command (set plugin options)
- aliases are executed before WeeChat/IRC commands, add `/builtin` command
- add `/cycle` command, `/part` command does close buffer anymore

### Internationalization

- add Russian translations (thanks to Pavel Shevchuk)

### Bug fixes

- fix `/squery` command (message sent to server, now OK with more than two arguments)
- fix `/alias` command (with an alias name, display content)
- add lock for log file (~/.weechat/weechat.log), only one WeeChat process can use this file ([bug #16382](https://savannah.nongnu.org/bugs/?16382))
- fix crash with malformed UTF-8 strings
- fix crash with ncurses color when too many colors defined in ncurses ([bug #16556](https://savannah.nongnu.org/bugs/?16556))
- fix bug with long outgoing IRC messages (> 512 bytes) ([bug #16358](https://savannah.nongnu.org/bugs/?16358))
- fix Ruby crash when handler does not return OK or KO ([bug #16552](https://savannah.nongnu.org/bugs/?16552))
- fix UTF-8 display bug with chars using more than one cell on screen ([bug #16356](https://savannah.nongnu.org/bugs/?16356))
- fix display bug with DCC file size when > 1 GB
- fix refresh bug (deadlock in curses) when terminal is resized ([bug #16542](https://savannah.nongnu.org/bugs/?16542))
- fix nicklist sort bug
- fix crash when multiple pv have same name: now it's forbidden and pv buffer is not renamed (when a nick changes) if another exists with same name ([bug #16369](https://savannah.nongnu.org/bugs/?16369))
- command `/clear [-all]` now clears hotlist
- fix crash after `/upgrade` if a line in history is empty ([bug #16379](https://savannah.nongnu.org/bugs/?16379))
- fix many crashes with DCC chat ([bug #16416](https://savannah.nongnu.org/bugs/?16416))
- fix commands 332, 333 (`/topic` now OK when channel is not opened)
- remove color encoding and charset conversion for commands (only allowed in text sent to channel/private)
- fix `/names` command: now displays result when not on a channel
- fix refresh bug (too many refresh) when terminal is resized
- fix nicklist display bugs when on top or bottom of chat window
- fix high CPU usage when running under a Screen that has been killed

### Documentation

- add German doc (thanks to Frank Zacharias)

### Build

- fix --disable-plugins option in configure script
- improve Lua detection ([bug #16574](https://savannah.nongnu.org/bugs/?16574))

## Version 0.1.8 (2006-03-18)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- improve alias completion (now uses target command for completion)
- add missing IRC command (487)
- add inactivity time, available for plugins via get_info("inactivity")
- add keys `Alt`+`Home` / `Alt`+`End` to scroll top/bottom, `Alt`+`F11` / `Alt`+`F12` to scroll nicklist top/bottom
- add special names for plugin message handlers: weechat_pv, weechat_highlight, weechat_ctcp, weechat_dcc
- add IRC raw data buffer (new key: `Alt`+`j`, `Alt`+`r`)
- add new plugins functions: add_timer_handler, remove_timer_handler, remove_infobar
- plugin messages handlers now called when message is ignored (by `/ignore`)
- new behavior for messages ignored by a message handler: now WeeChat executes standard handler, treating message as "ignored"
- many commands allowed for aliases
- many commands allowed when connecting to server
- add Lua script plugin
- add functions in plugins API: get_server_info, free_server_info, get_channel_info, free_channel_info, get_nick_info, free_nick_info
- add option "look_nick_complete_first" (patch from Gwenn)
- add option "look_open_near_server" (patch from Gwenn)
- add new scroll keys for a few lines up/down (default: `Alt`+`PgUp` / `Alt`+`PgDn`) (patch from Pistos)
- add new option "irc_away_check_max_nicks" to disable away check on channels with high number of nicks (patch from Gwenn)
- add new command line argument for setting WeeChat home dir (-d or --dir) (patch from Gwenn)
- add option "irc_show_away_once", to show away message only once in pv

### Internationalization

- add partial Hungarian translations

### Bug fixes

- improve Ruby plugin
- fix `/set` command when internal server name contains one or many dots
- fix get_info plugin API function when no server at all is opened
- fix display bug when top of buffer is displayed and first line is removed (according to "history_max_lines" setting)
- fix `/mode` command output
- fix completion problem in private with nicks
- script plugins now load scripts in WeeChat system share directory
- `/msg` command does not open any buffer anymore
- fix crash when using global history (when older entry is removed)
- fix display bug with `/kill` command
- fix bug with `/upgrade` and servers buffer
- fix bug with get_dcc_info plugin interface function
- fix bug with charset in infobar highlights
- fix bug with buffer detection in plugins/scripts commands
- fix bug with `/history` command

## Version 0.1.7 (2006-01-14)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- remove "irc_default_msg_away" setting, for RFC 2812 conformity (`/away` command without argument only removes away status), new values for "irc_display_away" (off, local, channel)
- add color for window separators (when split)
- add completion system for plugins/scripts commands
- add charset by server and channel, new command: `/charset`
- add Ruby script plugin
- add `/upgrade` command
- add ETA (Estimated Time of Arrival) for DCC files
- `/nick` command is now allowed when not connected to server
- add server/channel argument to `/buffer` command for jumping to buffer
- add new keys for switching to other windows: `Alt`+`w`, `Alt`+`Arrow`
- add new keys for scrolling to previous/next highlight: `Alt`+`p` / `Alt`+`n`
- add "read marker": an indicator for first unread line in a server or channel buffer (new key `Alt`+`u` to scroll to marker)
- new window management: custom size for windows, auto resize when terminal is resized
- add `/history` command

### Bug fixes

- fix msg command (now allowed in private buffer with "*" as target)
- fix refresh bug with Solaris when term size is changed
- fix plugins autoload
- fix display bug in chat window when a message length equals to window width
- fix infinite loop when resizing term to small size

### Build

- replace Texinfo doc by XML Docbook

## Version 0.1.6 (2005-11-11)

_If you are upgrading: please see [UPGRADING.md](UPGRADING.md)._

### New features

- new color management system, IRC colors are now correctly displayed and can be removed by new options irc_colors_receive and irc_colors_send
- add setting for having one server buffer for all servers (look_one_server_buffer)
- add setting for ignoring some chars when completing nicks
- signal SIGPIPE is now ignored
- add partial match for highlights
- add dcc_own_ip and dcc_port_range settings
- full UTF-8 support, auto-detection of UTF-8 usage (locale)
- add "Day changed to [date]" message when day changes
- new plugin interface, rewritten from scratch: now loads dynamic C library, and perl/python are script plugins
- log options (for server/channel/private) can now be set while WeeChat is running
- add channel modes +e and +f
- add some missing IRC commands, fix command 367
- add colors for input buffer and current channel of status bar
- add online help for config options (with `/set` full_option_name)
- enhanced "smart" hotlist, with names (new options: look_hotlist_names_{count|level|length})

### Bug fixes

- fix scroll problem when one line is bigger than screen size
- fix IRC message parser bug

## Version 0.1.5 (2005-09-24)

### New features

- add `/ame` command (send CTCP action to all channels of all connected servers)
- add setting "irc_notice_as_pv" to see notices as pv
- add nicks colors in setup file
- add some missing IRC commands
- add `/ignore` and `/unignore` commands
- signal SIGQUIT is now ignored
- jump to next server now saves current channel buffer for each server
- add keys `Ctrl`+`Up` / `Ctrl`+`Down` to call previous/next command in global history (common to all buffers)

### Bug fixes

- fix DCC bug: delete failed file only if really empty (on disk)
- fix IRC message parser bug
- fix scroll problem (screen moving when scrolling and new line displayed)
- fix infinite loop when scrolling back and displaying long lines
- fix crash when closing a buffer used by more than one window
- fix DCC display bug (now decodes string according to charset)
- fix bug with strings comparison (str[n]casecmp) and some locales (like Turkish), now using ASCII comparison (thanks to roktas)
- fix refresh bug when one line is bigger than screen size
- fix look_nicklist_min_size and look_nicklist_max_size options
- fix refresh bug when changing channel modes

## Version 0.1.4 (2005-07-30)

### New features

- join and part/quit prefixes (arrows) now displayed with different colors
- add "irc_highlight" setting, to get highlight with any word
- add `/amsg` command (send text to all channels of all connected servers)
- add color for private in hotlist (different than color for highlight)
- add DCC resume and timeout
- add function for Perl/Python to get DCC list
- new keyboard management: keys are setup in config file, add new command `/key`, add some new default keys, `Alt`+`k` is used to grab key (useful for `/key` command)
- add seconds in infobar time (optional thanks to new setting)
- add auto-prefix with "#" for channels (if no prefix found), with `/join` command

### Bug fixes

- fix auto-rejoin for channels with key
- fix `/ctcp` command (now any command/data allowed)
- fix SIGSEGV handler (now write a core file by aborting program)
- fix statusbar & infobar background refresh problem with some systems
- fix FIFO pipe (command now authorized on a buffer not connected to an IRC server)
- topic completion now decodes UTF-8 string
- fix bug with IRC URL on command line (irc://)
- fix some curses refreshes

## Version 0.1.3 (2005-07-02)

### New features

- proxy support (http, socks4, socks5) with authentication (http, socks5) and ipv6 support (client to proxy)
- add completion for config option (with `/set` command)
- commands from users outside channel now authorized (if special user or channel without "n" flag)
- add IPv6 support
- kill command now received and displayed
- add SSL support
- channel notify levels are saved in config file (new option "server_notify_levels" for server sections)
- part message now accepts %v (replaced by WeeChat version), like quit message

### Bug fixes

- errors while loading perl scripts are now displayed in server buffer (instead of current buffer)
- in python scripts, all messages written in stdin and stderr are redirected in server buffer
- fix a filename error while loading a python script manually
- fix plugins print and prnt functions: now OK for writing on server buffers
- fix color problem with new libcurses version
- fix crash when using `Alt`+`s` or `Alt`+`x` on DCC buffer (`Alt`+`d`)
- fix startup crash when config file (~/.weechat/weechat.rc) is not found

### Build

- improve Perl/Python libs detection for ./configure script

## Version 0.1.2 (2005-05-21)

### New features

- add Python plugin support, improve Perl interface (and now Perl/Python libraries are checked by configure script)
- add nicklist scroll keys (`Alt`+`Home` / `Alt`+`End` / `Alt`+`PgUp` / `Alt`+`PgDn` or `F11` / `F12`)
- add transfer rate for DCC files
- add `-all` option for `/nick` command
- buffers timestamp can now be changed (new option in config file)
- add missing IRC commands (307, 341, 485, 671)

### Bug fixes

- fix nicklist sort
- fix crash when purging old DCC
- fix crash with 64-bits arch (like AMD64) when converting UTF-8

### Build

- WeeChat now OK under *BSD and macOS

## Version 0.1.1 (2005-03-20)

### New features

- add nicks count for channel buffers
- add FIFO pipe for remote control
- add crash dump when WeeChat receives SIGSEGV (Segmentation fault)
- add new display engine: doesn't cut words at end of lines
- add DCC send and DCC chat
- add `/halfop` and `/dehalfop` commands, fix halfop display bug in nicklist
- add `/ban`, `/unban` and `/kickban` commands
- add --irc-commands and --weechat-commands command line options
- connection to IRC server is now made by child process (non blocking)
- add support for UnrealIrcd ("~" for chan owner, "&" for chan admin)
- new key for window switch (now: `F5` / `F6` = switch buffer, `F7` / `F8` = switch window)
- on server buffer, only server messages are logged
- improve `/help` command output
- plugins messages are logged with new config option (log_plugin_msg)

### Internationalization

- add Spanish translations

### Bug fixes

- fix `/kick` command
- fix `/invite` command (and now invite requests are displayed)
- fix `/buffer close` command (now OK when disconnected from server)
- fix display bugs when many windows are opened

## Version 0.1.0 (2005-02-12)

### New features

- improve `/window` command: now split and merge are OK
- away nicks are now displayed with another color (new option: "irc_away_check")
- add away indicator in status bar
- add lag indicator (and auto-disconnect after a delay if important lag)
- improve completion: now completes commands arguments (IRC and internal), when only one completion matches, completion mechanism is stopped (to complete command argument for example)
- improve `/set` command: empty strings are allowed, new colors, server options can be changed while WeeChat is running
- add default away/part/quit messages in config file
- new [irc] section in config file, move option "look_display_away" to "irc_display_away"
- server messages & errors are all prefixed (by 3 chars, like "-@-")
- add new options for charset (UTF-8 support): look_charset_decode, look_charset_encode and look_charset_internal

### Bug fixes

- fix many memory leaks
- fix colors bug: remove "gray" color (replaced by "default"), colors are OK when terminal has white (or light) background
- fix crash when resizing terminal to small size
- fix crash when multiple servers and big messages received from server
- fix crash when closing some private buffers
- fix crash when unknown section with option(s) in config file
- fix `/op`, `/deop`, `/voice`, `/devoice` (now OK with many nicks)
- fix `/me` command (now OK without parameter)
- fix `/away` command (now OK if not away)
- logs are now disabled by default (server/channel/private)

## Version 0.0.9 (2005-01-01)

### New features

- auto-reconnection to server (new options: server_autoreconnect (on/off), server_autoreconnect_delay (in seconds))
- new command `/buffer close` (close any server/channel/private buffer)
- new keys: `Ctrl`+`a` (home), `Ctrl`+`e` (end), `Ctrl`+`w` (same as `Ctrl`+`Backspace`), `Alt`+`s` (switch to server buffer), `Alt`+`x` (switch to first channel of next server)
- add new config option: "server_command_delay" (delay in seconds after startup command for each server)

### Bug fixes

- fix major bug when socket is closed by server (100% CPU usage), and disconnections are now OK (all channels are "closed", history is still visible, and buffer will be used again if reconnection to server)
- option "look_remove_colors_from_msgs" is now working
- fix display of nick mode changes
- fix `/notice` command (and display when received from server)

## Version 0.0.8 (2004-10-30)

### New features

- nickserv passwords hidden (new config option: log_hide_nickserv_pwd on/off)
- auto-rejoin channels when kicked (new config option: server_autorejoin on/off)
- add IRC::command function for Perl scripts
- `/buffer` command developed (buffers list, move and notify)
- logging buffers to disk (server/channel/private according to user preferences)
- add config option "look_display_away" to announce away in channels
- DCC file receive OK (`Alt`+`d` for DCC view)
- add key `Ctrl`+`l` (`L`) for redrawing terminal
- add key `Alt`+`r` for clearing hotlist

### Bug fixes

- fix `/kick` command: now OK with many words as reason
- fix bug when adding alias with same name as other
- fix crash when resizing terminal to very small size
- "-MORE-" message is now erased when switching to another buffer
- `/query` command now reopens private buffer if already opened

## Version 0.0.7 (2004-08-08)

### New features

- new "col_status_delimiters" config option
- add command `/buffer`, buffers ordered by number, auto-jump to active buffers (`Alt`+`a`), jump to buffers by number (`Alt`+`0`…`9`)
- add command `/window`, split terminal horizontally/vertically
- unique color for each nick (based on nickname)
- add history limit (text buffer and commands)

### Bug fixes

- action messages are now considered as messages, not crappy joins/parts
- fix display bug when nicklist is displayed at bottom of screen

### Build

- replace --enable-debug with --with-debug option for ./configure

## Version 0.0.6 (2004-06-05)

### New features

- improve channel highlight (priority to message vs join/part)
- add command `/query` (starts private conversation)
- add IRC messages 476, 477

### Bug fixes

- fix bug when opened private win and remote user changes his nick
- `/mode` command is now OK and channel flags are displayed in status bar
- fix display bug (text was blinking when scrolling)
- CTCP Version reply is now in English only and doesn't show host (security reason)

## Version 0.0.5 (2004-02-07)

### New features

- `/set` command to modify config options when WeeChat is running
- URL command line parameter to connect to server(s)
- new Perl script function to display message in info bar ("IRC::print_infobar")
- info bar highlight notifications
- add info bar timestamp in config ("look_infobar_timestamp")
- add info bar (optional, "look_infobar" to enable it, "on" by default)
- add -c (or --config) command line parameter to see config file options

### Bug fixes

- fix look_nicklist config option, now enables/disables nicklist
- secure code to prevent buffer overflows and memory leaks
- fix QUIT IRC command: now sent to all connected servers (not only current)
- fix crash with `/oper` command
- for default config file, nick is now based on un*x username
- fix crash when config file cannot be written
- add highlight on action messages

## Version 0.0.4 (2004-01-01)

### New features

- add Perl plugin

### Bug fixes

- fix switch to private buffer
- add highlight when our nick is written in a channel/private window
- catch `Ctrl`+`c` (ignored)

### Build

- debug messages can be enabled via ./configure --enable-debug option

## Version 0.0.3 (2003-11-03)

### New features

- add new IRC commands: stats, service, squit, motd, lusers, links, time, trace, admin, info, servlist, squery, who, whowas, die, summon, users, wallops, userhost, ison, ctcp ping

### Internationalization

- add French translations

### Bug fixes

- for sort of nicks (op, halfop, voice, other)
- fix problem with "353" IRC message (nicklist)
- fix problem when nick is truncated by server
- fix crash when entering text without any server connection
- fix crash when `/set` command is executed
- fix display bug (text was blinking when scrolling)
- code cleanup

### Build

- add ./configure script to build WeeChat

## Version 0.0.2 (2003-10-05)

### New features

- add commands `/rehash` and `/restart`
- and command and auto-join channels when connected to server
- new commands for alias: `/alias`, `/unalias` (new section in config file)
- config is now saved automatically when quitting WeeChat, add `/save` command
- new commands for servers: `/server`, `/connect`, `/disconnect`
- add autoconnect flag for each server in config file
- add "look_set_title" option in config file
- term window title is modified with WeeChat name and version
- CTCP version returns more info (about OS)

### Bug fixes

- fix nicklist display bug
- fix crash when sending command which can only be received

## Version 0.0.1 (2003-09-27)

### New features

- ncurses GUI with color output
- multi-servers
- channel windows, with nicklist (position: top, bottom, left or right)
- private windows
- IRC commands: away, ctcp, deop, devoice, invite, join, kick, kill, list, me, mode, msg, names, nick, notice, op, oper, part, ping, pong, quit, quote, topic, version, voice, whois
- WeeChat commands: clear, help, set (partial)
- many config options
- log file (~/.weechat/weechat.log)
- nicklist can be moved on top, bottom, left or right of window
