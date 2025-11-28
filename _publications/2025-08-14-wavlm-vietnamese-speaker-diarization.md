---
title: "Adapting WavLM for Vietnamese Speaker Diarization in Real-world Conversations"
collection: publications
category: conferences
permalink: /publication/2025-08-14-wavlm-vietnamese-speaker-diarization
excerpt: ''
date: 2025-08-14
venue: '2025 International Conference on Multimedia Analysis and Pattern Recognition (MAPR)'
slidesurl: ''
paperurl: 'https://doi.org/10.1109/MAPR67746.2025.11133848'
citation: 'Tuan-Duy Thang, Van-Huy Nguyen, Tri-Nhan Do, Quoc-Khanh Nguyen, Trung-Kien Phan, Dang-Khoa Mac (2025), "Adapting WavLM for Vietnamese Speaker Diarization in Real-world Conversations", 2025 International Conference on Multimedia Analysis and Pattern Recognition (MAPR), pp. 1-6.'
---
While end-to-end neural diarization (EEND) models have achieved state-of-the-art performance, their effectiveness in low-resource languages such as Vietnamese remains underexplored due to the lack of annotated conversational data. In this study, we adapt WavLM-based speaker diarization to Vietnamese by fine-tuning the DiariZen model with Vietnamese speech data. Additionally, we introduce ViYT-Diar, a high-quality benchmark of manually annotated Vietnamese dialogues. Experimental results show that our fine-tuned model achieves a DER of 11.76% on the English CALLHOME two-speaker test set and 2.38% on ViYT-Diar, significantly outperforming Pyannote 3.1 and Falcon API. Furthermore, our custom clustering pipeline maintains stable performance across chunk sizes (2.38% – 2.59% DER), whereas off-the-shelf clustering degrades from 9.73% to 3.75%. These results underscore the effectiveness of language-specific fine-tuning and tailored clustering for low-resource speaker diarization.

