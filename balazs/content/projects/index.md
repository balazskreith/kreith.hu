+++
draft = false
comments = false
slug = ""
tags = []
categories = []

showpagemeta = false
showcomments = false
+++

## Objective Quality for WebRTC conferences

Objective Quality is an indicator metric of the quality of WebRTC conferences. The
metric is used to evaluate conferences at callstats.io.

__Blogpost__: [Objective Quality v3](https://www.callstats.io/blog/2018/03/01/product-update-objective-quality-version-3)

## MPRTP plugin for Gstreamer

Multipath extension of Real-Time Protocol (MPRTP) makes real-time multimedia communication
capable of transferring on multiple path. To realize it a Gstreamer plugin is developed
capable of sending and receiving packets on multiple path.

__State__: Active

__Source__: https://github.om/balazskreith/gst-mprtp

### FRACTaL Congestion Control Algorithm

[FRACTaL]() is a congestion control algorithm developed for real-time interactive multimedia communications.
It uses FEC packets not only to protect multimedia streams, but also to explore available bandwidth capabilities.

__State__: Finished

__Publications and appearances__:

 - [1] [Early announcement](https://www.callstats.io/blog/2016/11/14/fec-congestion-control)
 - [2] [Conference report](https://www.callstats.io/blog/2017/10/16/acm-multimedia)
 - [3] [Conference paper](https://www.researchgate.net/publication/320419511_FRACTaL_FEC-based_Rate_Control_for_RTP)
 - [4] [Congestion control schemes](https://www.callstats.io/blog/2016/11/01/schemes-of-congestion-control) 

## Network Traffic Rate Tracker

Network Traffic Rate Tracker (NTRT) is yet another analytical tool for network monitoring.
The aim of the project is to create a lightweight low-level fast packet monitoring tool
in order to track, and accumulate network traffics going through network interfaces.

__State__: Infrequently maintained

__Description and source code__: https://github.com/balazskreith/ntrt


## Devclego

Devclego is a skeleton application to create maintainable services in a low-level programming
language capable of processing data and react to external events.
The skeleton contains libraries and predefined macros for threading,
making connectable components and create finite state machines.

__State__: Active

__Description and source code__: https://github.com/balazskreith/devclego

## Multiple-tau hardware correlators

An improved multiple-tau hardware correlator design is introduced for computing fluorescence correlation functions (CFs) in real time. Use of hardware resources is minimized by scheduling the computation of different segments of the CFs on a single correlator block. Simultaneous calculation of two multiple-tau autocorrelation (ACFs) and two cross-correlation functions (CCFs) is implemented in LabVIEW on a National Instruments field programmable gate array (FPGA) card with a minimal sampling time of 400 ns. Raw data are stored with a time resolution of 50 ns. The design can be easily adapted to other FPGA cards and extended to more inputs.

__State__: Finished in 2012

__Publications__:

 - [1] [Multiplexed multiple-tau auto- and cross-correlators](https://arxiv.org/abs/1112.1616)
 - [2] [FPGA implementation of a 32x32 autocorrelator array for analysis of fast image series](https://arxiv.org/abs/1112.1619)

## Shoprenter filtering system

Shoprenter is one of the largest webshop renting system in Hungary,
where webshops contain different type of products, which have different type of attributes.
The goal of the project was to create a filtering system that suitable for all customer needs,
in terms of restrict lists satisfies conditions, meanwhile the system must be as fast as possible.
My role was to design the database and client libraries.

__State__: Finished in 2012.  

__Company__: https://www.shoprenter.hu/
