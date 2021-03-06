$engine: 2
name: PlumeESX
version: v1.0.0
author: Tabarra & Chip
description: A full featured (13 jobs) and highly configurable yet lightweight ESX v1-final base that can be easily extended. 

tasks:
  # Download default CFX resources
   - action: download_github
    src: https://github.com/citizenfx/cfx-server-data
    ref: 88f4f974b855e0bf2ca5f51b9916648bd5b7d44b
    subpath: resources
    dest: ./resources
  
  # Download and prepare server.cfg / loadingscreen / database
  - action: download_github
    src: https://github.com/tabarra/PlumeESX-recipe
    ref: engine-2
    dest: ./tmp/plume_esx

  - action: move_path
    src: ./tmp/plume_esx/server.cfg
    dest: ./server.cfg
  
  - action: move_path
    src: ./tmp/plume_esx/loadingscreen
    dest: ./resources/loadingscreen

  - action: connect_database
  - action: query_database
    file: ./tmp/plume_esx/plume.sql
  - action: query_database
    file: ./tmp/plume_esx/gcphone.sql

  # Download basic resources and ESX dependencies
  - action: download_github
    src: https://github.com/Blumlaut/EasyAdmin
    ref: 4a2c04c44b4c4a3084a5641e82d61632faa8b913
    dest: ./resources/EasyAdmin

  - action: download_github
    src: https://github.com/esx-framework/async
    ref: 12dd585b0b4965596487f12039ce6f0ab4de319a
    dest: ./resources/async

  - action: download_github
    src: https://github.com/brouznouf/fivem-mysql-async
    ref: c5fa317a65acfe2eef453257e19e3b4fde137089
    dest: ./resources/mysql-async

  - action: download_github
    src: https://github.com/esx-framework/cron
    ref: 89914888d7dd801fb8430aeb386fd423e0f86f46
    dest: ./resources/cron

  - action: download_github
    src: https://github.com/esx-framework/skinchanger
    ref: f79ad3fb01f4b29408d251d2b7a45dd9c6f3ba31
    dest: ./resources/skinchanger

  - action: download_github
    src: https://github.com/HypeLevels/simpledrift
    ref: 77e378a2b59fcaca7624cb51575b2a3d39e3b635
    dest: ./resources/simpledrift

  - action: download_github
    src: https://github.com/dsheedes/cd_easytime
    ref: 60b93883d921488039e6a0f6596568cc4afc67c3
    dest: ./resources/cd_easytime

  - action: download_github
    src: https://github.com/Bob74/bob74_ipl
    ref: 8b81571f069cafb4a739b19101a48574f9361575
    dest: ./resources/bob74_ipl

  - action: download_github
    src: https://github.com/ali-exacute/esx_adminplus
    ref: 8894c8f0acbcd045f9ebe25031df663e544ce154
    dest: ./resources/esx_adminplus

  # Download ESX resources
  - action: download_github
    src: https://github.com/esx-framework/es_extended
    ref: legacy
    dest: ./resources/[esx]/es_extended

  - action: download_github
    src: https://github.com/esx-framework/esx_menu_default
    ref: 2d46087ade9369c46df1d80b706dc13e6e4ac673
    dest: ./resources/[esx]/esx_menu_default

  - action: download_github
    src: https://github.com/esx-framework/esx_menu_dialog
    ref: 1f53d642aa5867fd7762e1c98454d616e2a66f6a
    dest: ./resources/[esx]/esx_menu_dialog

  - action: download_github
    src: https://github.com/esx-framework/esx_menu_list
    ref: c4c88a9afd475074213d2586d09ac091c389c369
    dest: ./resources/[esx]/esx_menu_list

  - action: download_github
    src: https://github.com/esx-framework/esx_datastore
    ref: dfe0321bdd7ba35b6ec3316529c220b827816997
    dest: ./resources/[esx]/esx_datastore

  - action: download_github
    src: https://github.com/esx-framework/esx_identity
    ref: cade18e2de2f2084b2880031b3e8425d1433ad5f
    dest: ./resources/[esx]/esx_identity

  - action: download_github
    src: https://github.com/esx-framework/esx_skin
    ref: fd64bebb474d6e353ac36508e90dd1677daa841b
    dest: ./resources/[esx]/esx_skin

  - action: download_github
    src: https://github.com/esx-framework/esx_status
    ref: bce4abf4b507fa453a550fdbd25e2f3b2efe7064
    dest: ./resources/[esx]/esx_status

  - action: download_github
    src: https://github.com/esx-framework/esx_basicneeds
    ref: 9a35c8f53fd2f9f2ca481fe9e9eba876c214db74
    dest: ./resources/[esx]/esx_basicneeds

  - action: download_github
    src: https://github.com/esx-framework/esx_billing
    ref: eb06fd169dce4e89c668410c10a5cefd06650aef
    dest: ./resources/[esx]/esx_billing

  - action: download_github
    src: https://github.com/esx-framework/esx_addoninventory
    ref: 5709570bc2cda27e08159536e3a6c9d1a3734915
    dest: ./resources/[esx]/esx_addoninventory

  - action: download_github
    src: https://github.com/esx-framework/esx_addonaccount
    ref: 3573919be24068283a3103a08414f64398381513
    dest: ./resources/[esx]/esx_addonaccount

  - action: download_github
    src: https://github.com/esx-framework/esx_society
    ref: af56efc19cfbaa2541f9aaef46046d20ba6ec9bb
    dest: ./resources/[esx]/esx_society

  - action: download_github
    src: https://github.com/esx-framework/esx_license
    ref: 4a791b81827f17f7e31aeac1fb15f3c9c9ec6764
    dest: ./resources/[esx]/esx_license

  - action: download_github
    src: https://github.com/esx-framework/esx_service
    ref: 487a53693fda846e7a86ad8a3385dbe760ee8944
    dest: ./resources/[esx]/esx_service

  - action: download_github
    src: https://github.com/esx-framework/esx_garage
    ref: 6ae703b18965452d148541c061f830469c8a8bd9
    dest: ./resources/[esx]/esx_garage

  - action: download_github
    src: https://github.com/esx-framework/esx_vehicleshop
    ref: 79e10361bb3607f152a2887b5b45ff998e840d52
    dest: ./resources/[esx]/esx_vehicleshop

  - action: download_github
    src: https://github.com/esx-framework/esx_jobs
    ref: ae8e70044395be14d72d90e3301c45f6fb15ea27
    dest: ./resources/[esx]/esx_jobs

  - action: download_github
    src: https://github.com/esx-framework/esx_joblisting
    ref: bbce9722a24269e667d00cc26b7c6408f29cdfb7
    dest: ./resources/[esx]/esx_joblisting

  - action: download_github
    src: https://github.com/esx-framework/esx_policejob
    ref: 9ceb66a591bca41ab10786bc795ebf04e52e2877
    dest: ./resources/[esx]/esx_policejob

  - action: download_github
    src: https://github.com/esx-framework/esx_ambulancejob
    ref: e567948b9c78b0136bb08baeb8592d9e406ad2f3
    dest: ./resources/[esx]/esx_ambulancejob

  - action: download_github
    src: https://github.com/esx-framework/esx_mechanicjob
    ref: aa11285d5cb39a82926e5842ad89f0e890dab797
    dest: ./resources/[esx]/esx_mechanicjob

  - action: download_github
    src: https://github.com/esx-framework/esx_taxijob
    ref: 1893ad065a53c144babe466bde74c9b1241ec663
    dest: ./resources/[esx]/esx_taxijob

  - action: download_github
    src: https://github.com/esx-framework/esx_lscustom
    ref: 011a548e7428c0be43223585c60eaf43ca5ee004
    dest: ./resources/[esx]/esx_lscustom

  - action: download_github
    src: https://github.com/esx-framework/esx_shops
    ref: d8715d347c874905813446bfe2b810e63f19681b
    dest: ./resources/[esx]/esx_shops

  - action: download_github
    src: https://github.com/esx-framework/esx_weaponshop
    ref: b42afd53e3f9876c357962a9d79d86dc6919fde0
    dest: ./resources/[esx]/esx_weaponshop

  - action: download_github
    src: https://github.com/esx-framework/esx_clotheshop
    ref: 04183ae7c0a9c1505b37a13bb4e2bbd195862511
    dest: ./resources/[esx]/esx_clotheshop

  - action: download_github
    src: https://github.com/esx-framework/esx_barbershop
    ref: 423cf1cecb59c05a60ad908cc3574665f455cc3f
    dest: ./resources/[esx]/esx_barbershop

  - action: download_github
    src: https://github.com/esx-framework/esx_drugs
    ref: 5b5a612f2580c8dea1d17029f9f25cf201575ef7
    dest: ./resources/[esx]/esx_drugs

  - action: download_github
    src: https://github.com/esx-framework/esx_holdup
    ref: 1f3779c265db5cd9039b91633d9d86b5293d8d4b
    dest: ./resources/[esx]/esx_holdup

  ## GCPhone stuff
  - action: download_file
    url: https://github.com/Re-Ignited-Development/Re-Ignited-Phone/releases/download/V1.5/resources-1.2.zip
    path: ./tmp/gcphone.zip
  - action: unzip
    src: ./tmp/gcphone.zip
    dest: ./tmp
  - action: move_path
    src: ./tmp/resources-1.2/gcphone
    dest: ./resources/gcphone
  

  ## KL HUD v2
  - action: download_github
    src: https://github.com/Kilichi/Kl_HudV2
    ref: ac8a321ff335706509bdc6122a2984a80082e669
    dest: ./resources/Kl_HudV2

  - action: replace_string
    file: ./resources/[esx]/esx_status/client/main.lua
    search: 'esx_status:onTick'
    replace: 'Kl_Hud:onTick'


  ## Final touches
  - action: replace_string
    mode: all_vars
    file: ./resources/loadingscreen/config.js
    
  - action: remove_path
    path: ./tmp
