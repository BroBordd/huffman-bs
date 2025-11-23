# huffman_bs.py - BombSquad/Ballistica Network Packet Huffman Codec

This tool decompresses and compresses Huffman-encoded network packets used in
BombSquad (Ballistica engine). It can decode captured packets to understand their
structure and create new packets for testing or modding.

The Huffman encoding uses a static frequency table built from captured game traffic
to achieve ~40-60% compression on typical game packets.

# Usage
    # Decode a packet
    codec = HuffmanCodec()
    decompressed = codec.decompress(compressed_bytes)

    # Encode a packet
    compressed = codec.compress(scene_packet_bytes)
    full_packet = codec.encode_full_packet(scene_packet_bytes, client_id=0x7c)

# Based on
Ballistica source code
    src/ballistica/scene_v1/support/huffman.cc
    src/ballistica/base/networking/networking.h
