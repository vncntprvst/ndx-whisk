Overview
========

.. note::
    ndx-whisk is an NWB extension to store whisker tracking measurements. It is intended to convert measurements files generated by Whisk (Janelia Whisker Tracker) but is compatible with other whisker tracking methods.

    Whiskers measurments are saved into a DynamicTable with the following columns / data types (some columns are optional):
    'frame_id' (uint32) - the frame number
    'whisker_id' (uint16) - the whisker id number
    'label' (uint16) - the whisker label, according to its order on the face or post classification
    'length' (float32) - the length of the whisker
    'score' (float32) - the median score of the whisker tracing (optimal correlation between a parameterized filter and the image at points along the whisker)
    'pixel_length' (uint16) - the integer length of the whisker in pixels
    'angle' (float32) - the angle of the whisker
    'curvature' (float32) - the curvature of the whisker (reciprocal of the radius of curvature)
    'follicle_x' (float32) - the x pixel coordinate of the whisker follicle (the end-point of a traced segment closest to the face)
    'follicle_y' (float32) - the y pixel coordinate of the whisker follicle (the end-point of a traced segment closest to the face)
    'tip_x' (float32) - the x pixel coordinate of the whisker tip (the end-point of a traced segment furthest from the face)
    'tip_y' (float32) - the y pixel coordinate of the whisker tip (the end-point of a traced segment furthest from the face)
    'face_x' (int32) - the x pixel coordinate of the center of the whisker pad
    'face_y' (int32) - the y pixel coordinate of the center of the whisker pad
    'chunk_start' (uint32) - the chunk number, when the video recording is sliced into chunks for parallel processing

    The DynamicTable is then added to a ProcessingModule for behavioral data and the ProcessingModule is added to the NWBFile.